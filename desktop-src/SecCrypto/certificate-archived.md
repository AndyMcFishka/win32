﻿---
Description: 'Sets or retrieves a Boolean value that indicates whether the certificate is archived.'
ms.assetid: 'a6526b0e-e76b-4f03-a6ba-9e380e362364'
title: 'Certificate.Archived property'
---

# Certificate.Archived property

\[CAPICOM is a 32-bit only component that is available for use in the following operating systems: Windows Server 2008, Windows Vista, and Windows XP. Instead, use the [**X509Certificate2 Class**](T:System.Security.Cryptography.X509Certificates.X509Certificate2) in the [**System.Security.Cryptography.X509Certificates**](frlrfSystemSecurityCryptographyX509Certificates) namespace.\]

The **Archived** property sets or retrieves a Boolean value that indicates whether the certificate is archived.

This property is read/write.

## Syntax


```VB
Certificate.Archived As Boolean
```



## Property value

A Boolean value that indicates whether the certificate is archived. If **true**, the certificate is archived. Note that changing the value from **false** to **true** archives the certificate.

## Remarks

This property raises CAPICOM\_E\_NOT\_ALLOWED when it is scripted from a web-based application.

> [!Note]  
> An archived certificate is not visible in the certificate management user interface. Also, archived certificates will not be included in the [**Store.Open**](store-open.md) method unless CAPICOM\_STORE\_OPEN\_INCLUDE\_ARCHIVED is specified.

 

## Requirements



|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| End of client support<br/> | Windows Vista<br/>                                                               |
| End of server support<br/> | Windows Server 2008<br/>                                                         |
| Redistributable<br/>       | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>                   | <dl> <dt>Capicom.dll</dt> </dl> |



 

 



