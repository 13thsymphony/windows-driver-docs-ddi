---
UID: NE:d3dumddi._DXVADDI_VIDEOCHROMASUBSAMPLING
title: "_DXVADDI_VIDEOCHROMASUBSAMPLING"
author: windows-driver-content
description: The DXVADDI_VIDEOCHROMASUBSAMPLING enumeration type contains values that identify the chroma encoding scheme for Y'Cb'Cr' data.
old-location: display\dxvaddi_videochromasubsampling.htm
old-project: display
ms.assetid: 697b6ac2-9d25-42ad-aac5-44754f19bf2c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXVADDI_VIDEOCHROMASUBSAMPLING, d3dumddi/DXVADDI_VideoChromaSubsamplingMask, d3dumddi/DXVADDI_VideoChromaSubsampling_Horizontally_Cosited, d3dumddi/DXVADDI_VIDEOCHROMASUBSAMPLING, d3dumddi/DXVADDI_VideoChromaSubsampling_MPEG1, DXVADDI_VideoChromaSubsampling_Horizontally_Cosited, DXVADDI_VideoChromaSubsampling_Unknown, DXVADDI_VideoChromaSubsampling_Vertically_Cosited, d3dumddi/DXVADDI_VideoChromaSubsampling_Cosited, d3dumddi/DXVADDI_VideoChromaSubsampling_Vertically_Cosited, DXVADDI_VideoChromaSubsampling_DV_PAL, DXVADDI_VIDEOCHROMASUBSAMPLING enumeration [Display Devices], d3dumddi/DXVADDI_VideoChromaSubsampling_ProgressiveChroma, d3dumddi/DXVADDI_VideoChromaSubsampling_Unknown, d3dumddi/DXVADDI_VideoChromaSubsampling_MPEG2, display.dxvaddi_videochromasubsampling, DXVADDI_VideoChromaSubsampling_Cosited, DXVADDI_VideoChromaSubsamplingMask, DXVA2_Structs_19b84102-b287-43e4-87e5-98bcc8b2bec8.xml, DXVADDI_VideoChromaSubsampling_MPEG1, DXVADDI_VideoChromaSubsampling_MPEG2, DXVADDI_VIDEOCHROMASUBSAMPLING, d3dumddi/DXVADDI_VideoChromaSubsampling_DV_PAL, DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes, DXVADDI_VideoChromaSubsampling_ProgressiveChroma, d3dumddi/DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	DXVADDI_VIDEOCHROMASUBSAMPLING
product: Windows
targetos: Windows
req.typenames: DXVADDI_VIDEOCHROMASUBSAMPLING
---

# _DXVADDI_VIDEOCHROMASUBSAMPLING Enumeration
The DXVADDI_VIDEOCHROMASUBSAMPLING enumeration type contains values that identify the chroma encoding scheme for Y'Cb'Cr' data.

## Syntax
````
typedef enum _DXVADDI_VIDEOCHROMASUBSAMPLING { 
  DXVADDI_VideoChromaSubsamplingMask                             = 0x0F,
  DXVADDI_VideoChromaSubsampling_Unknown                         = 0,
  DXVADDI_VideoChromaSubsampling_ProgressiveChroma               = 0x8,
  DXVADDI_VideoChromaSubsampling_Horizontally_Cosited            = 0x4,
  DXVADDI_VideoChromaSubsampling_Vertically_Cosited              = 0x2,
  DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes  = 0x1,
  DXVADDI_VideoChromaSubsampling_MPEG2                           = DXVADDI_VideoChromaSubsampling_Horizontally_Cosited | DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes,
  DXVADDI_VideoChromaSubsampling_MPEG1                           = DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes,
  DXVADDI_VideoChromaSubsampling_DV_PAL                          = DXVADDI_VideoChromaSubsampling_Horizontally_Cosited | DXVADDI_VideoChromaSubsampling_Vertically_Cosited,
  DXVADDI_VideoChromaSubsampling_Cosited                         = DXVADDI_VideoChromaSubsampling_Horizontally_Cosited | DXVADDI_VideoChromaSubsampling_Vertically_Cosited | DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes
} DXVADDI_VIDEOCHROMASUBSAMPLING;
````

## Constants

<table>
            
                <tr>
                    <td>DXVADDI_VideoChromaSubsampling_Cosited</td>
                    <td>A bitwise OR of the <b>DXVADDI_VideoChromaSubsampling_Horizontally_Cosited</b>, and <b>DXVADDI_VideoChromaSubsampling_Vertically_Cosited</b>, and <b>DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes</b> values that are used with 4:4:4, 4:2:2, and 4:1:1 data.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoChromaSubsampling_DV_PAL</td>
                    <td>A bitwise OR of the <b>DXVADDI_VideoChromaSubsampling_Horizontally_Cosited</b> and <b>DXVADDI_VideoChromaSubsampling_Vertically_Cosited</b> values that are used with 4:2:0 data.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoChromaSubsampling_Horizontally_Cosited</td>
                    <td>Chroma samples are aligned on multiples of the luma samples horizontally.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoChromaSubsampling_MPEG1</td>
                    <td>The <b>DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes</b> value that is used with 4:2:0 data.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoChromaSubsampling_MPEG2</td>
                    <td>A bitwise OR of the <b>DXVADDI_VideoChromaSubsampling_Horizontally_Cosited</b> and <b>DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes</b> values that are used with 4:2:0 data.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoChromaSubsampling_ProgressiveChroma</td>
                    <td>The video chroma subsampling is progressive.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoChromaSubsampling_Unknown</td>
                    <td>The video chroma subsampling is not specified.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes</td>
                    <td>The Pb and Pr (or Cb and Cr) planes have the same phase alignment. This value can be set only to 0 in the <b>VideoChromaSubsampling</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a> structure if the data is vertically cosited.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoChromaSubsampling_Vertically_Cosited</td>
                    <td>Chroma samples are aligned on multiples of the luma samples vertically.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoChromaSubsamplingMask</td>
                    <td>The video chroma subsampling mask. The first four (0x0F) bits of a DWORD can be used to specify video chroma subsampling.</td>
                </tr>
</table>

    ## Remarks

        A bitwise OR of the values of DXVADDI_VIDEOCHROMASUBSAMPLING can be used to create a value in the <b>VideoChromaSubsampling</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a> structure.

Cosite variations indicate that the chroma samples are aligned with the luma samples. Typically, 4:2:0 data with chroma is aligned in one or more directions with the luma data. Note that 4:4:4, 4:2:2, and 4:1:1 data are always cosited in both directions.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

    ## See Also

        <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOCHROMASUBSAMPLING enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>