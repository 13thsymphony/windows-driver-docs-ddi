---
UID: NE:rilapitypes.RILUICCRECORDSTATUSPARAMMASK
title: RILUICCRECORDSTATUSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccrecordstatusparammask_2.htm
old-project: netvista
ms.assetid: d0aad2bc-9b14-4468-92cf-b5757e43fde0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILUICCRECORDSTATUSPARAMMASK, RILUICCRECORDSTATUSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_URS_ALL, RIL_PARAM_URS_FILELOCKSTATUS, RIL_PARAM_URS_ITEMCOUNT, RIL_PARAM_URS_SIZE, netvista.riluiccrecordstatusparammask_2, rilapitypes/RILUICCRECORDSTATUSPARAMMASK, rilapitypes/RIL_PARAM_URS_ALL, rilapitypes/RIL_PARAM_URS_FILELOCKSTATUS, rilapitypes/RIL_PARAM_URS_ITEMCOUNT, rilapitypes/RIL_PARAM_URS_SIZE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
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
req.product: Windows 10 or later.
---

# RILUICCRECORDSTATUSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCRECORDSTATUSPARAMMASK { 
  RIL_PARAM_URS_ITEMCOUNT,
  RIL_PARAM_URS_SIZE,
  RIL_PARAM_URS_FILELOCKSTATUS,
  RIL_PARAM_URS_ALL
} RILUICCRECORDSTATUSPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_URS_RECORDTYPE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_URS_ITEMCOUNT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_URS_SIZE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_URS_FILELOCKSTATUS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_URS_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |