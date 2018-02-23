---
UID: NE:ntddrilapitypes.RILNETWORKCODEPARAMMASK
title: RILNETWORKCODEPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILNETWORKCODEPARAMMASK.
old-location: netvista\rilnetworkcodeparammask.htm
old-project: netvista
ms.assetid: 10842352-4201-477f-b1ea-8ed9181a6012
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapitypes/RIL_PARAM_NETWORKCODE_RI, RILNETWORKCODEPARAMMASK, RIL_PARAM_NETWORKCODE_MNC, rilapitypes/RIL_PARAM_NETWORKCODE_NID, rilapitypes/RILNETWORKCODEPARAMMASK, RIL_PARAM_NETWORKCODE_SID, RIL_PARAM_NETWORKCODE_ALL, rilapitypes/RIL_PARAM_NETWORKCODE_SID, RIL_PARAM_NETWORKCODE_EXECUTOR, RIL_PARAM_NETWORKCODE_MCC, rilapitypes/RIL_PARAM_NETWORKCODE_ALL, netvista.rilnetworkcodeparammask, RIL_PARAM_NETWORKCODE_RI, RILNETWORKCODEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_NETWORKCODE_NID, rilapitypes/RIL_PARAM_NETWORKCODE_EXECUTOR, rilapitypes/RIL_PARAM_NETWORKCODE_MCC, rilapitypes/RIL_PARAM_NETWORKCODE_MNC
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILNETWORKCODEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILNETWORKCODEPARAMMASK
---

# RILNETWORKCODEPARAMMASK Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILNETWORKCODEPARAMMASK.

## Syntax
````
enum RILNETWORKCODEPARAMMASK {
  RIL_PARAM_NETWORKCODE_EXECUTOR  = 0x00000001, 
  RIL_PARAM_NETWORKCODE_MCC       = 0x00000002, 
  RIL_PARAM_NETWORKCODE_MNC       = 0x00000004, 
  RIL_PARAM_NETWORKCODE_SID       = 0x00000008, 
  RIL_PARAM_NETWORKCODE_NID       = 0x00000010, 
  RIL_PARAM_NETWORKCODE_RI        = 0x00000020, 
  RIL_PARAM_NETWORKCODE_ALL       = 0x0000003F 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_NETWORKCODE_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NETWORKCODE_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NETWORKCODE_MCC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NETWORKCODE_MNC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NETWORKCODE_NID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NETWORKCODE_RI</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NETWORKCODE_SID</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h, Ntddrilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILNETWORKCODEPARAMMASK enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>