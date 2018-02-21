---
UID: NE:rilapitypes.RILUICCRECORDTYPE
title: RILUICCRECORDTYPE
author: windows-driver-content
description: This enumeration describes the RILUICCRECORDTYPE.
old-location: netvista\riluiccrecordtype.htm
old-project: netvista
ms.assetid: 962970e2-1861-4872-b0f3-db307f36d5d8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_UICCRECORDTYPE_LINEAR, rilapitypes/RIL_UICCRECORDTYPE_CYCLIC, RIL_UICCRECORDTYPE_MASTER, RIL_UICCRECORDTYPE_TRANSPARENT, rilapitypes/RIL_UICCRECORDTYPE_BERTLV, rilapitypes/RIL_UICCRECORDTYPE_MASTER, RIL_UICCRECORDTYPE_CYCLIC, RILUICCRECORDTYPE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_UICCRECORDTYPE_LINEAR, rilapitypes/RILUICCRECORDTYPE, RIL_UICCRECORDTYPE_BERTLV, RIL_UICCRECORDTYPE_UNKNOWN, RILUICCRECORDTYPE, rilapitypes/RIL_UICCRECORDTYPE_UNKNOWN, netvista.riluiccrecordtype, rilapitypes/RIL_UICCRECORDTYPE_TRANSPARENT
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
-	RILUICCRECORDTYPE
product: Windows
targetos: Windows
req.typenames: RILUICCRECORDTYPE
req.product: Windows 10 or later.
---

# RILUICCRECORDTYPE Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCRECORDTYPE.

## Syntax
````
enum RILUICCRECORDTYPE {
  RIL_UICCRECORDTYPE_UNKNOWN      = 0x00000000, 
  RIL_UICCRECORDTYPE_TRANSPARENT  = 0x00000001, 
  RIL_UICCRECORDTYPE_CYCLIC       = 0x00000002, 
  RIL_UICCRECORDTYPE_LINEAR       = 0x00000003, 
  RIL_UICCRECORDTYPE_BERTLV       = 0x00000004, 
  RIL_UICCRECORDTYPE_MASTER       = 0x00000005 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_UICCRECORDTYPE_BERTLV</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCRECORDTYPE_CYCLIC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCRECORDTYPE_DEDICATED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCRECORDTYPE_LINEAR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCRECORDTYPE_MASTER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCRECORDTYPE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCRECORDTYPE_TRANSPARENT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCRECORDTYPE_UNKNOWN</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCRECORDTYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>