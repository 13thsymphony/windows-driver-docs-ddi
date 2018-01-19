---
UID : NE:dxva._DXVA_VideoTransferMatrix
title : _DXVA_VideoTransferMatrix
author : windows-driver-content
description : The DXVA_VideoTransferMatrix enumeration type contains enumerators that identify the conversion matrix from Y'Cb'Cr' to R'G'B'.
old-location : display\dxva_videotransfermatrix.htm
old-project : display
ms.assetid : 726ce165-fd07-4dd3-a004-8081481340a1
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXVA_VideoTransferMatrix, DXVA_VideoTransferMatrix
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : dxva.h
req.include-header : Dxva.h
req.target-type : Windows
req.target-min-winverclnt : This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXVA_VideoTransferMatrix
req.alt-loc : dxva.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : DXVA_VideoTransferMatrix
---

# _DXVA_VideoTransferMatrix Enumeration
The DXVA_VideoTransferMatrix enumeration type contains enumerators that identify the conversion matrix from Y'Cb'Cr' to R'G'B'.

## Syntax
````
typedef enum _DXVA_VideoTransferMatrix { 
  DXVA_VideoTransferMatrixShift       = (DXVA_ExtColorData_ShiftBase + 7),
  DXVA_VideoTransferMatrixMask        = DXVAColorMask(3, DXVA_VideoTransferMatrixShift),
  DXVA_VideoTransferMatrix_Unknown    = 0,
  DXVA_VideoTransferMatrix_BT709      = 1,
  DXVA_VideoTransferMatrix_BT601      = 2,
  DXVA_VideoTransferMatrix_SMPTE240M  = 3
} DXVA_VideoTransferMatrix;
````

## Constants

<table>

<tr>
<td>DXVA_VideoTransferMatrix_BT601</td>
<td>Specifies the BT601 transfer matrix.</td>
</tr>

<tr>
<td>DXVA_VideoTransferMatrix_BT709</td>
<td>Specifies the BT709 transfer matrix.</td>
</tr>

<tr>
<td>DXVA_VideoTransferMatrix_SMPTE240M</td>
<td>Specifies a HD video standard rarely used in Japan.</td>
</tr>

<tr>
<td>DXVA_VideoTransferMatrix_Unknown</td>
<td>Specifies that the video transfer matrix is not specified. The default is BT601 for standard definition (SD) video and BT709 for high definition (HD) video.</td>
</tr>

<tr>
<td>DXVA_VideoTransferMatrixMask</td>
<td>Specifies the video transfer matrix mask. 3 (0x00038000) bits of a DWORD can be used to specify video transfer matrix.</td>
</tr>

<tr>
<td>DXVA_VideoTransferMatrixShift</td>
<td>Specifies to shift bits by 15 positions (DXVA_ExtColorData_ShiftBase + 7, or 8 + 7).</td>
</tr>
</table>

## Remarks

One of the enumerators of DXVA_VideoTransferMatrix can be specified in the <b>VideoTransferMatrix</b> member of the <a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dxva.h (include Dxva.h) |

## See Also

<dl>
<dt>
<a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoTransferMatrix enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>