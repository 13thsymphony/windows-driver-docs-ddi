---
UID: NE:ntddrilapitypes.RILIMSIPARAMMASK
title: RILIMSIPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILIMSIPARAMMASK.
old-location: netvista\rilimsiparammask.htm
old-project: netvista
ms.assetid: 8fe1ecda-4b2f-4a6f-b02c-7e50630614eb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapitypes/RIL_PARAM_IMSI_IMSI, RIL_PARAM_IMSI_MCC, rilapitypes/RILIMSIPARAMMASK, rilapitypes/RIL_PARAM_IMSI_ALL, RILIMSIPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RILIMSIPARAMMASK, rilapitypes/RIL_PARAM_IMSI_MCC, netvista.rilimsiparammask, rilapitypes/RIL_PARAM_IMSI_MNC, RIL_PARAM_IMSI_IMSI, RIL_PARAM_IMSI_ALL, RIL_PARAM_IMSI_MNC
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
-	RILIMSIPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILIMSIPARAMMASK
---

# RILIMSIPARAMMASK Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILIMSIPARAMMASK.

## Syntax
````
enum RILIMSIPARAMMASK {
  RIL_PARAM_IMSI_IMSI  = 0x00000001, 
  RIL_PARAM_IMSI_MCC   = 0x00000002, 
  RIL_PARAM_IMSI_MNC   = 0x00000004, 
  RIL_PARAM_IMSI_ALL   = 0x00000007 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_IMSI_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_IMSI_IMSI</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_IMSI_MCC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_IMSI_MNC</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h, Ntddrilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILIMSIPARAMMASK enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>