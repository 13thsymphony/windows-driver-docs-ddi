---
UID : NS:d3dumddi._D3DDDICB_DEALLOCATE2
title : "_D3DDDICB_DEALLOCATE2"
author : windows-driver-content
description : The D3DDDICB_DEALLOCATE2 structure describes parameters for releasing allocations with pfnDeallocate2Cb.
old-location : display\d3dddicb_deallocate2.htm
old-project : display
ms.assetid : C859CB06-3F71-4F6D-9949-0E9AE75CEC20
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.d3dddicb_deallocate2, D3DDDICB_DEALLOCATE2 structure [Display Devices], d3dumddi/D3DDDICB_DEALLOCATE2, _D3DDDICB_DEALLOCATE2, D3DDDICB_DEALLOCATE2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
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
req.typenames : D3DDDICB_DEALLOCATE2
---

# _D3DDDICB_DEALLOCATE2 structure
The <b>D3DDDICB_DEALLOCATE2</b> structure describes parameters for releasing allocations with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocate2cb.md">pfnDeallocate2Cb</a>

## Syntax
````
typedef struct _D3DDDICB_DEALLOCATE2 {
  HANDLE                           hResource;
  UINT                             NumAllocations;
  const D3DKMT_HANDLE              *HandleList;
  D3DDDICB_DESTROYALLOCATION2FLAGS Flags;
} D3DDDICB_DEALLOCATE2;
````

## Members


`Flags`

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_destroyallocation2flags.md">D3DDDICB_DESTROYALLOCATION2FLAGS</a> structure that contains additional details about the operation.

`HandleList`

[in] An array of <b>D3DKMT_HANDLE</b> data types that represent kernel-mode handles to the allocations. The Direct3D runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function returns these handles. Therefore, the user-mode display driver uses these handles to release the allocations.

If the user-mode display driver sets the handle in the <b>hResource</b> member to non-<b>NULL</b>, <b>HandleList</b> is ignored by the Direct3D runtime.

`hResource`

[in] A handle to a resource whose associated allocations must be released. If the user-mode display driver uses the array that is specified by <b>HandleList</b> to specify the allocations to release, it sets <b>hResource</b> to <b>NULL</b>.

`NumAllocations`

[in] The number of allocations in the <b>HandleList</b> array. If the user-mode display driver sets the handle in the <b>hResource</b> member to non-<b>NULL</b>, <b>NumAllocations</b> is ignored by the Direct3D runtime.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocate2cb.md">pfnDeallocate2Cb</a>

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_destroyallocation2flags.md">D3DDDICB_DESTROYALLOCATION2FLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_DEALLOCATE2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>