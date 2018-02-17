---
UID: NS:d3dumddi._D3DDDIARG_BUFFERBLT
title: "_D3DDDIARG_BUFFERBLT"
author: windows-driver-content
description: The D3DDDIARG_BUFFERBLT structure describes the parameters of a buffer bit-block transfer (bitblt) operation.
old-location: display\d3dddiarg_bufferblt.htm
old-project: display
ms.assetid: 1d638aeb-299a-4707-be5d-99291a1605e0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_param_Structs_08885ff3-963c-4067-bddc-696b9cc96e1b.xml, display.d3dddiarg_bufferblt, D3DDDIARG_BUFFERBLT, _D3DDDIARG_BUFFERBLT, d3dumddi/D3DDDIARG_BUFFERBLT, D3DDDIARG_BUFFERBLT structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3DDDIARG_BUFFERBLT
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_BUFFERBLT
---

# _D3DDDIARG_BUFFERBLT structure
The D3DDDIARG_BUFFERBLT structure describes the parameters of a buffer bit-block transfer (bitblt) operation.

## Syntax
````
typedef struct _D3DDDIARG_BUFFERBLT {
  HANDLE      hDstResource;
  HANDLE      hSrcResource;
  UINT        Offset;
  D3DDDIRANGE SrcRange;
} D3DDDIARG_BUFFERBLT;
````

## Members


`hDstResource`

[in] A handle to the destination vertex or index buffer.

`hSrcResource`

[in] A handle to the source vertex or index buffer.

`Offset`

[in] The offset, in bytes, of the destination buffer that the copy should be directed into.

`SrcRange`

[in] A D3DDDIRANGE structure that indicates what range of the source buffer should be copied. This D3DDDIRANGE specifies an offset and size, in bytes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_bufblt.md">BufBlt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_BUFFERBLT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>