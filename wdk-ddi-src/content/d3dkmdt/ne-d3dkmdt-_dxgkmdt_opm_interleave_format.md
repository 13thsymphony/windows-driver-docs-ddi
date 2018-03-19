---
UID: NE:d3dkmdt._DXGKMDT_OPM_INTERLEAVE_FORMAT
title: "_DXGKMDT_OPM_INTERLEAVE_FORMAT"
author: windows-driver-content
description: The DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration indicates the scan line ordering of a video frame from a protected output's signal.
old-location: display\dxgkmdt_opm_interleave_format.htm
old-project: display
ms.assetid: beaee817-5a91-40df-8b29-4750e3c1600e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKMDT_OPM_INTERLEAVE_FORMAT, DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration [Display Devices], DXGKMDT_OPM_INTERLEAVE_FORMAT_FORCE_ULONG, DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_EVEN_FIRST, DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_ODD_FIRST, DXGKMDT_OPM_INTERLEAVE_FORMAT_OTHER, DXGKMDT_OPM_INTERLEAVE_FORMAT_PROGRESSIVE, DmEnums_7b247abd-613b-495b-aea0-d53d9b519525.xml, _DXGKMDT_OPM_INTERLEAVE_FORMAT, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_EVEN_FIRST, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_ODD_FIRST, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_OTHER, d3dkmdt/DXGKMDT_OPM_INTERLEAVE_FORMAT_PROGRESSIVE, display.dxgkmdt_opm_interleave_format
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	DXGKMDT_OPM_INTERLEAVE_FORMAT
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_INTERLEAVE_FORMAT
---

# _DXGKMDT_OPM_INTERLEAVE_FORMAT Enumeration
The DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration indicates the scan line ordering of a video frame from a protected output's signal.

## Syntax
````
typedef enum _DXGKMDT_OPM_INTERLEAVE_FORMAT { 
  DXGKMDT_OPM_INTERLEAVE_FORMAT_OTHER                   = 0,
  DXGKMDT_OPM_INTERLEAVE_FORMAT_PROGRESSIVE             = 2,
  DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_EVEN_FIRST  = 3,
  DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_ODD_FIRST   = 4,
  DXGKMDT_OPM_INTERLEAVE_FORMAT_FORCE_ULONG             = 0xFFFFFFFF
} DXGKMDT_OPM_INTERLEAVE_FORMAT;
````

## Constants

<table>
            
                <tr>
                    <td>DXGKMDT_OPM_INTERLEAVE_FORMAT_OTHER</td>
                    <td>Indicates that the video frame has a scan line ordering other than those given in the following constants of this enumeration.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_INTERLEAVE_FORMAT_PROGRESSIVE</td>
                    <td>Indicates that each video frame has a scan line ordering that is progressive (that is, not interlaced).</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_EVEN_FIRST</td>
                    <td>Indicates that each video frame has a scan line ordering that is interlaced, each field contains half of a frame, and the even scan lines are displayed first.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_INTERLEAVE_FORMAT_INTERLEAVED_ODD_FIRST</td>
                    <td>Indicates that each video frame has a scan line ordering that is interlaced, each field contains half of a frame, and the odd scan lines are displayed first.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_INTERLEAVE_FORMAT_FORCE_ULONG</td>
                    <td>Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_actual_output_format.md">DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT</a>