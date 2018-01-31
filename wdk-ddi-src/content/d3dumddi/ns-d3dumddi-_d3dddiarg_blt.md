---
UID : NS:d3dumddi._D3DDDIARG_BLT
title : "_D3DDDIARG_BLT"
author : windows-driver-content
description : The D3DDDIARG_BLT structure describes the parameters of a bit-block transfer (bitblt).
old-location : display\d3dddiarg_blt.htm
old-project : display
ms.assetid : 9663d0fe-7397-49d7-b860-e466a9311aca
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dumddi/D3DDDIARG_BLT, D3DDDIARG_BLT, UMDisplayDriver_param_Structs_1c7d23e1-c05e-42b6-802e-4a69a80006c8.xml, _D3DDDIARG_BLT, display.d3dddiarg_blt, D3DDDIARG_BLT structure [Display Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DDDIARG_BLT
---

# _D3DDDIARG_BLT structure
The D3DDDIARG_BLT structure describes the parameters of a bit-block transfer (bitblt).

## Syntax
````
typedef struct _D3DDDIARG_BLT {
  HANDLE          hSrcResource;
  UINT            SrcSubResourceIndex;
  RECT            SrcRect;
  HANDLE          hDstResource;
  UINT            DstSubResourceIndex;
  RECT            DstRect;
  UINT            ColorKey;
  D3DDDI_BLTFLAGS Flags;
} D3DDDIARG_BLT;
````

## Members


`ColorKey`

[in] A value for the color key. Note that the <b>SrcColorKey</b> and <b>DstColorKey</b> bit-field flags are never set simultaneously in the <b>Flags</b> member.

`DstRect`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure for the destination rectangle.

`DstSubResourceIndex`

[in] The index to the destination surface within the resource.

`Flags`

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_bltflags.md">D3DDDI_BLTFLAGS</a> structure that identifies the type of bitblt to perform. Note that some bit-field flags in this structure are mutually exclusive with other flags. For more information about these flags, see the following Remarks section.

`hDstResource`

[in] A handle to the destination resource.

`hSrcResource`

[in] A handle to the source resource.

`SrcRect`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure for the source rectangle.

`SrcSubResourceIndex`

[in] The index to the source surface within the resource.

## Remarks
If a filtering option (for example, the <b>Point</b> or <b>Linear</b> bit-field flag) is not specified in the <b>Flags</b> member, the driver can use its own filtering technique.

The <b>SrcColorKey</b> and <b>DstColorKey</b> bit-field flags are never set simultaneously. Similarly, the <b>Point</b> bit-field flag is not simultaneously set with the <b>Linear</b> bit-field flag.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_blt.md">Blt</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_bltflags.md">D3DDDI_BLTFLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_BLT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>