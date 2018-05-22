---
Description: 'Semisynchronous calls are the recommended means to call WMI methods, such as IWbemServices::ExecMethod and provider methods, such as the Chkdsk Method of the Win32\_LogicalDisk Class.'
audience: developer
author: 'REDMOND\\markl'
manager: 'REDMOND\\markl'
ms.assetid: '3d5ddd77-19f7-42d0-b8ca-a0a11f6b3f0f'
ms.prod: 'windows-server-dev'
ms.technology: 'windows-management-instrumentation'
ms.tgt_platform: multiple
title: Making a Semisynchronous Call with C++
---

# Making a Semisynchronous Call with C++

Semisynchronous calls are the recommended means to call WMI methods, such as [**IWbemServices::ExecMethod**](iwbemservices-execmethod.md) and provider methods, such as the [**Chkdsk Method of the Win32\_LogicalDisk Class**](https://msdn.microsoft.com/library/aa384913).

One disadvantage of synchronous processing is that the caller thread is blocked until the call completes. The blockage can cause a delay in processing time. In contrast, an asynchronous call must implement [**SWbemSink**](swbemsink.md) in script. In C++, asynchronous code must implement the [**IWbemObjectSink**](iwbemobjectsink.md) interface, use multiple threads, and control the flow of information back to the caller. Large result sets from queries, for example, can take a considerable amount of time to deliver and forces the caller to spend significant system resources to handle the delivery.

Semisynchronous processing solves both the thread blockage and uncontrolled delivery problems by polling a special status object that implements the [**IWbemCallResult**](iwbemcallresult.md) interface. Through **IWbemCallResult**, you can improve the speed and efficiency of queries, enumerations, and event notifications.

The following procedure describes how to make a semisynchronous call with the [**IWbemServices**](iwbemservices.md) interface.

**To make a semisynchronous call with the IWbemServices interface**

1.  Make your call as normal, but with the **WBEM\_FLAG\_RETURN\_IMMEDIATELY** flag set in the *IFlags* parameter.

    You can combine **WBEM\_FLAG\_RETURN\_IMMEDIATELY** with other flags that are valid for the specific method. For example, use the **WBEM\_FLAG\_FORWARD\_ONLY** flag for all calls that return enumerators. Setting these flags in combination saves time and space, and improves responsiveness.

2.  Poll for your results.

    If you call a method that returns an enumerator, such as [**IWbemServices::CreateClassEnum**](iwbemservices-createclassenum.md) or [**IWbemServices::ExecQuery**](iwbemservices-execquery.md), you can poll the enumerators with the [**IEnumWbemClassObject::Next**](ienumwbemclassobject-next.md) or [**IEnumWbemClassObject::NextAsync**](ienumwbemclassobject-nextasync.md) methods. The **IEnumWbemClassObject::NextAsync** call is nonblocking and returns immediately. In the background, WMI begins to deliver the requested number of objects by calling [**IWbemObjectSink::Indicate**](iwbemobjectsink-indicate.md). WMI then stops and waits for another **NextAsync** call.

    If you call a method that does not return an enumerator, such as [**IWbemServices::GetObject**](iwbemservices-getobject.md), you must set the *ppCallResult* parameter to a valid pointer. Use the [**IWbemCallResult::GetCallStatus**](iwbemcallresult-getcallstatus.md) on the returned pointer to retrieve **WBEM\_S\_NO\_ERROR**.

3.  Finish your call.

    For a call that returns an enumerator, WMI calls [**IWbemObjectSink::SetStatus**](iwbemobjectsink-setstatus.md) to report the completion of the operation. If you do not need the entire result, release the enumerator by calling the [**IEnumWbemClassObject**](ienumwbemclassobject.md)::[**Release**](_com_iunknown_release) method. Calling **Release** results in WMI canceling the delivery of all objects that remain.

    For a call that does not use an enumerator, retrieve the [**GetCallStatus**](iwbemcallresult-getcallstatus.md) object through the *plStatus* parameter of your method.

The C++ code example in this topic requires the following \#include statements to compile correctly.


```C++
#include <comdef.h>
#include <wbemidl.h>
```



The following code example shows how to make a semisynchronous call to [**GetObject**](iwbemservices-getobject.md).


```C++
void GetObjSemiSync(IWbemServices *pSvc)
{

    IWbemCallResult *pCallRes = 0;
    IWbemClassObject *pObj = 0;
    
    HRESULT hRes = pSvc->GetObject(_bstr_t(L"MyClass=\"AAA\""), 0,
        0, 0, &amp;pCallRes
        );
        
    if (hRes || pCallRes == 0)
        return;
        
    while (true)
    {
        LONG lStatus = 0;
        HRESULT hRes = pCallRes->GetCallStatus(5000, &amp;lStatus);
        if ( hRes == WBEM_S_NO_ERROR || hRes != WBEM_S_TIMEDOUT )
            break;

        // Do another task
    }

    hRes = pCallRes->GetResultObject(5000, &amp;pObj);
    if (hRes)
    {
        pCallRes->Release();
        return;
    }

    pCallRes->Release();

    // Use the object.

    // ...

    // Release it.
    // ===========
        
    pObj->Release();    // Release objects not owned.            
  
}
```



## Related topics

<dl> <dt>

[Calling a Method](calling-a-method.md)
</dt> </dl>

 

 


