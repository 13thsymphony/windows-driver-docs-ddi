---
UID: NE:ntddrilapitypes.RILUICCFILELOCKSTATUSPARAMMASK
title: RILUICCFILELOCKSTATUSPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILUICCFILELOCKSTATUSPARAMMASK.
old-location: netvista\riluiccfilelockstatusparammask.htm
old-project: netvista
ms.assetid: 341e11bb-957b-4745-9892-f1274ff97f44
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILUICCFILELOCKSTATUSPARAMMASK, RILUICCFILELOCKSTATUSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_UFLS_ACCESSCONDITION, RIL_PARAM_UFLS_ALL, RIL_PARAM_UFLS_PINREFERENCE, netvista.riluiccfilelockstatusparammask, rilapitypes/RILUICCFILELOCKSTATUSPARAMMASK, rilapitypes/RIL_PARAM_UFLS_ACCESSCONDITION, rilapitypes/RIL_PARAM_UFLS_ALL, rilapitypes/RIL_PARAM_UFLS_PINREFERENCE
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
-	RILUICCFILELOCKSTATUSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCFILELOCKSTATUSPARAMMASK
---

# RILUICCFILELOCKSTATUSPARAMMASK Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCFILELOCKSTATUSPARAMMASK.

## Syntax
````
enum RILUICCFILELOCKSTATUSPARAMMASK {
  RIL_PARAM_UFLS_ACCESSCONDITION  = 0x00000001, 
  RIL_PARAM_UFLS_PINREFERENCE     = 0x00000002, 
  RIL_PARAM_UFLS_ALL              = 0x00000003 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_UFLS_ACCESSCONDITION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UFLS_PINREFERENCE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UFLS_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h, Ntddrilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>