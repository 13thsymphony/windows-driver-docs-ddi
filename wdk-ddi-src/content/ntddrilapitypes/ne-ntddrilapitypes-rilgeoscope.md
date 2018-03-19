---
UID: NE:ntddrilapitypes.RILGEOSCOPE
title: RILGEOSCOPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgeoscope.htm
old-project: netvista
ms.assetid: 5dc49d01-54d2-48d3-8649-96262b890fc5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILGEOSCOPE, RILGEOSCOPE enumeration [Network Drivers Starting with Windows Vista], RIL_GEOSCOPE_CELL, RIL_GEOSCOPE_CELL_IMMEDIATE, RIL_GEOSCOPE_LOCATIONAREA, RIL_GEOSCOPE_MAX, RIL_GEOSCOPE_PLMN, netvista.rilgeoscope, ntddrilapitypes/RILGEOSCOPE, ntddrilapitypes/RIL_GEOSCOPE_CELL, ntddrilapitypes/RIL_GEOSCOPE_CELL_IMMEDIATE, ntddrilapitypes/RIL_GEOSCOPE_LOCATIONAREA, ntddrilapitypes/RIL_GEOSCOPE_MAX, ntddrilapitypes/RIL_GEOSCOPE_PLMN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILGEOSCOPE
product: Windows
targetos: Windows
req.typenames: RILGEOSCOPE
---

# RILGEOSCOPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILGEOSCOPE { 
  RIL_GEOSCOPE_CELL_IMMEDIATE,
  RIL_GEOSCOPE_LOCATIONAREA,
  RIL_GEOSCOPE_PLMN,
  RIL_GEOSCOPE_CELL,
  RIL_GEOSCOPE_MAX
} RILGEOSCOPE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_GEOSCOPE_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GEOSCOPE_CELL_IMMEDIATE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GEOSCOPE_LOCATIONAREA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GEOSCOPE_PLMN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GEOSCOPE_CELL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GEOSCOPE_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |