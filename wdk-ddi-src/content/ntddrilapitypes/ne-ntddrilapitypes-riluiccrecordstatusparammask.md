---
UID: NE:ntddrilapitypes.RILUICCRECORDSTATUSPARAMMASK
title: RILUICCRECORDSTATUSPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILUICCRECORDSTATUSPARAMMASK.
old-location: netvista\riluiccrecordstatusparammask.htm
old-project: netvista
ms.assetid: 6db3cdd2-3865-42d7-8b63-3dcacaec5941
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILUICCRECORDSTATUSPARAMMASK, RILUICCRECORDSTATUSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_URS_ALL, RIL_PARAM_URS_FILELOCKSTATUS, RIL_PARAM_URS_ITEMCOUNT, RIL_PARAM_URS_RECORDTYPE, RIL_PARAM_URS_SIZE, netvista.riluiccrecordstatusparammask, rilapitypes/RILUICCRECORDSTATUSPARAMMASK, rilapitypes/RIL_PARAM_URS_ALL, rilapitypes/RIL_PARAM_URS_FILELOCKSTATUS, rilapitypes/RIL_PARAM_URS_ITEMCOUNT, rilapitypes/RIL_PARAM_URS_RECORDTYPE, rilapitypes/RIL_PARAM_URS_SIZE
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
-	RILUICCRECORDSTATUSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCRECORDSTATUSPARAMMASK
---

# RILUICCRECORDSTATUSPARAMMASK Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCRECORDSTATUSPARAMMASK.

## Syntax
````
enum RILUICCRECORDSTATUSPARAMMASK {
  RIL_PARAM_URS_RECORDTYPE      = 0x00000001, 
  RIL_PARAM_URS_ITEMCOUNT       = 0x00000002, 
  RIL_PARAM_URS_SIZE            = 0x00000004, 
  RIL_PARAM_URS_FILELOCKSTATUS  = 0x00000008, 
  RIL_PARAM_URS_ALL             = 0x0000000F 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_URS_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_URS_FILELOCKSTATUS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_URS_ITEMCOUNT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_URS_RECORDTYPE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_URS_SIZE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h, Ntddrilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCRECORDSTATUSPARAMMASK enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>