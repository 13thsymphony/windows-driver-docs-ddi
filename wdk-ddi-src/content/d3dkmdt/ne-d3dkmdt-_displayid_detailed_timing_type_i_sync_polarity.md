---
UID: NE:d3dkmdt._DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY
title: "_DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY"
author: windows-driver-content
description: The DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration indicates the display device's sync polarity (whether the sync signal is positive or negative).
old-location: display\displayid_detailed_timing_type_i_sync_polarity.htm
old-project: display
ms.assetid: 6563d4f7-3750-49c1-80f5-14a839e70cb7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DIDDT1_Sync_Negative, DIDDT1_Sync_Positive, DmEnums_7a2bc957-2ae3-4a38-bbe7-8e3e52994e5d.xml, _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY, _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration [Display Devices], d3dkmdt/DIDDT1_Sync_Negative, d3dkmdt/DIDDT1_Sync_Positive, d3dkmdt/_DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY, display.displayid_detailed_timing_type_i_sync_polarity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	_DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY
product: Windows
targetos: Windows
req.typenames: 
---

# _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY Enumeration
The DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration indicates the display device's sync polarity (whether the sync signal is positive or negative).

## Syntax
````
enum _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY {
  DIDDT1_Sync_Positive  = 0, 
  DIDDT1_Sync_Negative  = 1 

};
````

## Constants

<table>
            
                <tr>
                    <td>DIDDT1_Sync_Negative</td>
                    <td>Indicates that the sync polarity is negative.</td>
                </tr>
            
                <tr>
                    <td>DIDDT1_Sync_Positive</td>
                    <td>Indicates that the sync polarity is positive.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of the Windows operating systems. Available in Windows 7 and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |