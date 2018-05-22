---
Description: 'Retrieves the current size, in bytes, of the free virtual address space available to the process.'
audience: developer
author: 'REDMOND\\markl'
manager: 'REDMOND\\markl'
ms.assetid: '13b3b347-5db1-484f-bd1d-3a604eb6bc5b'
ms.prod: 'windows-server-dev'
ms.technology:
- cimwin32
- 'windows-management-instrumentation'
ms.tgt_platform: multiple
title: 'GetAvailableVirtualSize method of the Win32\_Process class'
---

# GetAvailableVirtualSize method of the Win32\_Process class

Retrieves the current size, in bytes, of the free virtual address space available to the process.

## Syntax


```mof
uint32 GetAvailableVirtualSize(
  [out]�uint64 AvailableVirtualSize
);
```



## Parameters

<dl> <dt>

*AvailableVirtualSize* \[out\]
</dt> <dd>

The *AvailableVirtualSize* parameter returns the free virtual address space available to this process.

</dd> </dl>

## Return value

Returns zero (0) to indicate success. Any other number indicates an error. For additional error codes, see [**WMI Error Constants**](https://msdn.microsoft.com/library/aa394559) or [**WbemErrorEnum**](https://msdn.microsoft.com/library/aa393978). For general **HRESULT** values, see [System Error Codes](https://msdn.microsoft.com/library/windows/desktop/ms681381).

<dl> <dt>

**Successful completion**
</dt> <dd>

0

The operation completed successfully.

</dd> <dt>

**Access denied**
</dt> <dd>

2

The user does not have access to the requested information

</dd> <dt>

**Insufficient privilege**
</dt> <dd>

3

The user does not have sufficient privilege.

</dd> <dt>

**Unknown failure**
</dt> <dd>

8

Unknown failure.

</dd> <dt>

**Path not found**
</dt> <dd>

9

The path specified does not exist.

</dd> <dt>

**Invalid parameter**
</dt> <dd>

21

The specified parameter is invalid.

</dd> <dt>

**Other**
</dt> <dd>

22�4294967295

For values other than those listed, refer to the [System Error Codes](https://msdn.microsoft.com/library/windows/desktop/ms681381) documentation.

</dd> </dl>

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�8.1<br/>                                                                  |
| Minimum supported server<br/> | Windows Server�2012�R2<br/>                                                       |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                  |
| MOF<br/>                      | <dl> <dt>CIMWin32.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>CIMWin32.dll</dt> </dl> |



## See also

<dl> <dt>

[**Win32\_Process**](win32-process.md)
</dt> </dl>

�

�



