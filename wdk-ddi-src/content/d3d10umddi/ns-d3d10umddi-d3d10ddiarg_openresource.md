---
UID: NS.D3D10UMDDI.D3D10DDIARG_OPENRESOURCE
title: D3D10DDIARG_OPENRESOURCE
author: windows-driver-content
description: The D3D10DDIARG_OPENRESOURCE structure contains information for opening a shared resource.
old-location: display\d3d10ddiarg_openresource.htm
old-project: display
ms.assetid: acd1a957-9a1f-48a5-849b-e0cb9f8e05b6
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3D10DDIARG_OPENRESOURCE, D3D10DDIARG_OPENRESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10DDIARG_OPENRESOURCE
req.alt-loc: d3d10umddi.h
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

# D3D10DDIARG_OPENRESOURCE structure



## -description
The D3D10DDIARG_OPENRESOURCE structure contains information for opening a shared resource.



## -syntax

````
typedef struct D3D10DDIARG_OPENRESOURCE {
  UINT                      NumAllocations;
#if D3D10DDI_MINOR_HEADER_VERSION >= 2 || D3D11DDI_MINOR_HEADER_VERSION >= 1
  union {
    D3DDDI_OPENALLOCATIONINFO  *pOpenAllocationInfo;
    D3DDDI_OPENALLOCATIONINFO2 *pOpenAllocationInfo2;
  };
#else 
  D3DDDI_OPENALLOCATIONINFO *pOpenAllocationInfo;
#endif 
  D3D10DDI_HKMRESOURCE      hKMResource;
  VOID                      *pPrivateDriverData;
  UINT                      PrivateDriverDataSize;
} D3D10DDIARG_OPENRESOURCE;
````


## -struct-fields

### -field NumAllocations

[in] The number of elements in the array that the <b>pOpenAllocationInfo</b> member specifies. <b>NumAllocations</b> represents the number of allocations to open.


### -field pOpenAllocationInfo

[in] An array of <a href="display.d3dddi_openallocationinfo">D3DDDI_OPENALLOCATIONINFO</a> structures that describe the allocations in the resource to open.


### -field pOpenAllocationInfo2

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


### -field pOpenAllocationInfo

[in] An array of <a href="display.d3dddi_openallocationinfo">D3DDDI_OPENALLOCATIONINFO</a> structures that describe the allocations in the resource to open.


### -field hKMResource

[in] A D3D10DDI_HKMRESOURCE data type that represents a kernel-mode handle to the resource that is associated with the allocations. 

This kernel-mode handle represents an existing shared resource that was previously created through a call to the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a> function. 

The user-mode display driver can insert the kernel-mode resource handle in the command stream for subsequent use by the display miniport driver.


### -field pPrivateDriverData

[in] A pointer to private data that was passed to the display miniport driver when the resource was created. This data is per resource and not per allocation like the private data in each allocation's <a href="display.d3dddi_openallocationinfo">D3DDDI_OPENALLOCATIONINFO</a> structure. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>
</dt>
<dt>
<a href="display.d3dddi_openallocationinfo">D3DDDI_OPENALLOCATIONINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_OPENRESOURCE structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

