---
UID: NE:ntddrilapitypes.RILADDRESSNUMPLAN
title: RILADDRESSNUMPLAN
author: windows-driver-content
description: This enumeration describes the RILADDRESSNUMPLAN.
old-location: netvista\riladdressnumplan.htm
old-project: netvista
ms.assetid: fa25ce95-3eed-41f3-a0eb-5c290fa032e8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILADDRESSNUMPLAN, RILADDRESSNUMPLAN enumeration [Network Drivers Starting with Windows Vista], RIL_NUMPLAN_DATA, RIL_NUMPLAN_ERMES, RIL_NUMPLAN_NATIONAL, RIL_NUMPLAN_PRIVATE, RIL_NUMPLAN_TELEPHONE, RIL_NUMPLAN_TELEX, RIL_NUMPLAN_UNKNOWN, netvista.riladdressnumplan, rilapitypes/RILADDRESSNUMPLAN, rilapitypes/RIL_NUMPLAN_DATA, rilapitypes/RIL_NUMPLAN_ERMES, rilapitypes/RIL_NUMPLAN_NATIONAL, rilapitypes/RIL_NUMPLAN_PRIVATE, rilapitypes/RIL_NUMPLAN_TELEPHONE, rilapitypes/RIL_NUMPLAN_TELEX, rilapitypes/RIL_NUMPLAN_UNKNOWN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILADDRESSNUMPLAN
product: Windows
targetos: Windows
req.typenames: RILADDRESSNUMPLAN
---

# RILADDRESSNUMPLAN Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILADDRESSNUMPLAN.

## Syntax
````
enum RILADDRESSNUMPLAN {
  RIL_NUMPLAN_UNKNOWN    = 0x00000000, 
  RIL_NUMPLAN_TELEPHONE  = 0x00000001, 
  RIL_NUMPLAN_DATA       = 0x00000002, 
  RIL_NUMPLAN_TELEX      = 0x00000003, 
  RIL_NUMPLAN_NATIONAL   = 0x00000004, 
  RIL_NUMPLAN_PRIVATE    = 0x00000005, 
  RIL_NUMPLAN_ERMES      = 0x00000006 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_NUMPLAN_DATA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_NUMPLAN_ERMES</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_NUMPLAN_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_NUMPLAN_NATIONAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_NUMPLAN_PRIVATE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_NUMPLAN_TELEPHONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_NUMPLAN_TELEX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_NUMPLAN_UNKNOWN</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h, Ntddrilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILADDRESSNUMPLAN enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>