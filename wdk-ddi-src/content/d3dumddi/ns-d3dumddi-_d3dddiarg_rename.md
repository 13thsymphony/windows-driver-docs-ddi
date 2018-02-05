---
UID : NS:d3dumddi._D3DDDIARG_RENAME
title : "_D3DDDIARG_RENAME"
author : windows-driver-content
description : The D3DDDIARG_RENAME structure describes a resource or a surface within the resource to rename with a new allocation.
old-location : display\d3dddiarg_rename.htm
old-project : display
ms.assetid : 3ecddaf4-bce7-4ea0-b53d-e4872fa21f81
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DDDIARG_RENAME, D3DDDIARG_RENAME structure [Display Devices], display.d3dddiarg_rename, UMDisplayDriver_param_Structs_5acf671e-94e3-4752-89c1-b3c9e33cba7a.xml, d3dumddi/D3DDDIARG_RENAME, _D3DDDIARG_RENAME
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
req.typenames : D3DDDIARG_RENAME
---

# _D3DDDIARG_RENAME structure
The D3DDDIARG_RENAME structure describes a resource or a surface within the resource to rename with a new allocation.

## Syntax
````
typedef struct _D3DDDIARG_RENAME {
  HANDLE                 hResource;
  UINT                   SubResourceIndex;
  HANDLE                 hCookie;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7)
  D3DGPU_VIRTUAL_ADDRESS GpuVirtualAddress;
#endif 
} D3DDDIARG_RENAME;
````

## Members


`GpuVirtualAddress`

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.

`hCookie`

[in] A handle that represents the renamed surface instance that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function previously returned.

`hResource`

[in] A handle to the resource to be renamed.

`SubResourceIndex`

[in] The zero-based index into the resource that <b>hResource</b> specifies. This index indicates the subresource or surface to be renamed.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rename.md">Rename</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_RENAME structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>