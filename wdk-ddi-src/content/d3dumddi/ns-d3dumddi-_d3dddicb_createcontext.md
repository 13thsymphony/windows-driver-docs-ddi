---
UID: NS.D3DUMDDI._D3DDDICB_CREATECONTEXT
title: _D3DDDICB_CREATECONTEXT
author: windows-driver-content
description: The D3DDDICB_CREATECONTEXT structure describes a context to create.
old-location: display\d3dddicb_createcontext.htm
old-project: display
ms.assetid: 6bee57b5-f4b3-424c-aeb5-3bf65ab16392
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DDDICB_CREATECONTEXT, D3DDDICB_CREATECONTEXT
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
req.alt-api: D3DDDICB_CREATECONTEXT
req.alt-loc: d3dumddi.h
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
---

# _D3DDDICB_CREATECONTEXT structure



## -description
The D3DDDICB_CREATECONTEXT structure describes a context to create.



## -syntax

````
typedef struct _D3DDDICB_CREATECONTEXT {
  UINT                      NodeOrdinal;
  UINT                      EngineAffinity;
  D3DDDI_CREATECONTEXTFLAGS Flags;
  VOID                      *pPrivateDriverData;
  UINT                      PrivateDriverDataSize;
  HANDLE                    hContext;
  VOID                      *pCommandBuffer;
  UINT                      CommandBufferSize;
  D3DDDI_ALLOCATIONLIST     *pAllocationList;
  UINT                      AllocationListSize;
  D3DDDI_PATCHLOCATIONLIST  *pPatchLocationList;
  UINT                      PatchLocationListSize;
#if D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7
  D3DGPU_VIRTUAL_ADDRESS    CommandBuffer;
#endif 
} D3DDDICB_CREATECONTEXT;
````


## -struct-fields

### -field NodeOrdinal

[in] The zero-based index for the node that the context is scheduled on.


### -field EngineAffinity

[in] The zero-based index for the engine, within the node that <b>NodeOrdinal</b> specifies, that the context can run in.


### -field Flags

[in] A <a href="display.d3dddi_createcontextflags">D3DDDI_CREATECONTEXTFLAGS</a> structure that indicates, in bit-field flags, how to create the context. 


### -field pPrivateDriverData

[in] A pointer to private data that is passed to a display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


### -field hContext

[out] A handle to the context that the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function creates. 


### -field pCommandBuffer

[out] A pointer to the first command buffer for the created context.


### -field CommandBufferSize

[out] The size, in bytes, of the first command buffer for the created context, which <b>pCommandBuffer</b> points to. 


### -field pAllocationList

[out] An array of <a href="display.d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a> structures for the first allocation list for the created context.


### -field AllocationListSize

[out] The number of elements in the allocation-list array that <b>pAllocationList</b> specifies.


### -field pPatchLocationList

[out] An array of <a href="display.d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a> structures for the first patch-location list for the created context.


### -field PatchLocationListSize

[out] The number of elements in the patch-location-list array that <b>pPatchLocationList</b> specifies.


### -field CommandBuffer

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a>
</dt>
<dt>
<a href="display.d3dddi_createcontextflags">D3DDDI_CREATECONTEXTFLAGS</a>
</dt>
<dt>
<a href="display.d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_CREATECONTEXT structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

