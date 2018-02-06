---
UID: NE:rilapitypes.RILSYSTEMTYPE
title: RILSYSTEMTYPE
author: windows-driver-content
description: This enumeration represents RILSYSTEMTYPE.
old-location: netvista\rilsystemtype.htm
old-project: netvista
ms.assetid: 5a95969c-d7cd-4afa-affa-7095979ee56b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_SYSTEMTYPE_ALL, rilapitypes/RIL_SYSTEMTYPE_UMTS, rilapitypes/RIL_SYSTEMTYPE_GSM, RIL_SYSTEMTYPE_CDMA, RIL_SYSTEMTYPE_GSMUMTS, RIL_SYSTEMTYPE_TDSCDMA, rilapitypes/RIL_SYSTEMTYPE_ALL, rilapitypes/RIL_SYSTEMTYPE_EVDO, RIL_SYSTEMTYPE_EVDO, RILSYSTEMTYPE, rilapitypes/RIL_SYSTEMTYPE_TDSCDMA, RILSYSTEMTYPE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_SYSTEMTYPE_GSMUMTS, RIL_SYSTEMTYPE_GSM, RIL_SYSTEMTYPE_NONE, rilapitypes/RIL_SYSTEMTYPE_LTE, netvista.rilsystemtype, rilapitypes/RIL_SYSTEMTYPE_1XRTT, rilapitypes/RIL_SYSTEMTYPE_CDMA, RIL_SYSTEMTYPE_1XRTT, RIL_SYSTEMTYPE_LTE, rilapitypes/RIL_SYSTEMTYPE_NONE, rilapitypes/RILSYSTEMTYPE, RIL_SYSTEMTYPE_UMTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	RILSYSTEMTYPE
product: Windows
targetos: Windows
req.typenames: RILSYSTEMTYPE
req.product: Windows 10 or later.
---

# RILSYSTEMTYPE Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration represents RILSYSTEMTYPE.

## Syntax
````
enum RILSYSTEMTYPE {
  RIL_SYSTEMTYPE_NONE     = 0x00000000, 
  RIL_SYSTEMTYPE_1XRTT    = 0x00000001, 
  RIL_SYSTEMTYPE_EVDO     = 0x00000002, 
  RIL_SYSTEMTYPE_GSM      = 0x00000004, 
  RIL_SYSTEMTYPE_UMTS     = 0x00000008, 
  RIL_SYSTEMTYPE_LTE      = 0x00000010, 
  RIL_SYSTEMTYPE_TDSCDMA  = 0x00000020, 
  RIL_SYSTEMTYPE_CDMA     = RIL_SYSTEMTYPE_1XRTT | RIL_SYSTEMTYPE_EVDO, 
  RIL_SYSTEMTYPE_GSMUMTS  = RIL_SYSTEMTYPE_GSM | RIL_SYSTEMTYPE_UMTS, 
  RIL_SYSTEMTYPE_ALL      = 0x0000003F 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_1XRTT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_3GPP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_CDMA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_EVDO</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_GSM</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_GSMTDS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_GSMUMTS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_GSMUMTSTDS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_LTE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_TDSCDMA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMTYPE_UMTS</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

    ## See Also

        <a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILSYSTEMTYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>