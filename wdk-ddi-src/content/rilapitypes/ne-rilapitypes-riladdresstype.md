---
UID: NE:rilapitypes.RILADDRESSTYPE
title: RILADDRESSTYPE
author: windows-driver-content
description: This enumeration describes the RILADDRESSTYPE.
old-location: netvista\riladdresstype.htm
old-project: netvista
ms.assetid: a9fe509e-ef15-49ac-beca-339e3582d16e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapitypes/RIL_ADDRTYPE_NATIONAL, RIL_ADDRTYPE_NATIONAL, RILADDRESSTYPE, rilapitypes/RIL_ADDRTYPE_SUBSCRIBER, RIL_ADDRTYPE_INTERNATIONAL, RIL_ADDRTYPE_EMAIL, RIL_ADDRTYPE_ABBREV, rilapitypes/RIL_ADDRTYPE_IP, RIL_ADDRTYPE_ALPHANUM, rilapitypes/RIL_ADDRTYPE_EMAIL, rilapitypes/RIL_ADDRTYPE_ALPHANUM, rilapitypes/RILADDRESSTYPE, RILADDRESSTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_ADDRTYPE_SUBSCRIBER, rilapitypes/RIL_ADDRTYPE_INTERNATIONAL, netvista.riladdresstype, rilapitypes/RIL_ADDRTYPE_NETWKSPECIFIC, rilapitypes/RIL_ADDRTYPE_ABBREV, rilapitypes/RIL_ADDRTYPE_UNKNOWN, RIL_ADDRTYPE_NETWKSPECIFIC, RIL_ADDRTYPE_IP, RIL_ADDRTYPE_UNKNOWN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILADDRESSTYPE
product: Windows
targetos: Windows
req.typenames: RILADDRESSTYPE
req.product: Windows 10 or later.
---

# RILADDRESSTYPE Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILADDRESSTYPE.

## Syntax
````
enum RILADDRESSTYPE {
  RIL_ADDRTYPE_UNKNOWN        = 0x00000000, 
  RIL_ADDRTYPE_INTERNATIONAL  = 0x00000001, 
  RIL_ADDRTYPE_NATIONAL       = 0x00000002, 
  RIL_ADDRTYPE_NETWKSPECIFIC  = 0x00000003, 
  RIL_ADDRTYPE_SUBSCRIBER     = 0x00000004, 
  RIL_ADDRTYPE_ALPHANUM       = 0x00000005, 
  RIL_ADDRTYPE_ABBREV         = 0x00000006, 
  RIL_ADDRTYPE_IP             = 0x00000007, 
  RIL_ADDRTYPE_EMAIL          = 0x00000008 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_ADDRTYPE_ABBREV</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ADDRTYPE_ALPHANUM</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ADDRTYPE_EMAIL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ADDRTYPE_INTERNATIONAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ADDRTYPE_IP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ADDRTYPE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ADDRTYPE_NATIONAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ADDRTYPE_NETWKSPECIFIC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ADDRTYPE_SUBSCRIBER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ADDRTYPE_UNKNOWN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ADDRTYPE_URI</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h, Ntddrilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILADDRESSTYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>