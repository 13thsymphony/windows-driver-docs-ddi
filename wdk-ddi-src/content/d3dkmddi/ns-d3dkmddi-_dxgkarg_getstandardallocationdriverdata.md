---
UID: NS.D3DKMDDI._DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
title: _DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
author: windows-driver-content
description: The DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure describes a standard allocation type.
old-location: display\dxgkarg_getstandardallocationdriverdata.htm
old-project: display
ms.assetid: 4327ba59-bd74-4018-85d2-54a1693c62c1
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA, DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
req.alt-loc: d3dkmddi.h
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
---

# _DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure



## -description
The DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure describes a standard allocation type.


## -syntax

````
typedef struct _DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA {
  D3DKMDT_STANDARDALLOCATION_TYPE StandardAllocationType;
  union {
    D3DKMDT_SHAREDPRIMARYSURFACEDATA *pCreateSharedPrimarySurfaceData;
    D3DKMDT_SHADOWSURFACEDATA        *pCreateShadowSurfaceData;
    D3DKMDT_STAGINGSURFACEDATA       *pCreateStagingSurfaceData;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7)
    D3DKMDT_GDISURFACEDATA           *pCreateGdiSurfaceData;
#endif 
  };
  VOID                            *pAllocationPrivateDriverData;
  UINT                            AllocationPrivateDriverDataSize;
  VOID                            *pResourcePrivateDriverData;
  UINT                            ResourcePrivateDriverDataSize;
} DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA;
````


## -struct-fields

### -field StandardAllocationType

[in] A <a href="display.d3dkmdt_standardallocation_type">D3DKMDT_STANDARDALLOCATION_TYPE</a>-typed value that identifies the type of standard allocation to describe.

### -field pCreateSharedPrimarySurfaceData

[in] A pointer to a <a href="display.d3dkmdt_sharedprimarysurfacedata">D3DKMDT_SHAREDPRIMARYSURFACEDATA</a> structure, if <b>StandardAllocationType</b> specifies D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE.

### -field pCreateShadowSurfaceData

[in] A pointer to a <a href="display.d3dkmdt_shadowsurfacedata">D3DKMDT_SHADOWSURFACEDATA</a> structure, if <b>StandardAllocationType</b> specifies D3DKMDT_STANDARDALLOCATION_SHADOWSURFACE.

### -field pCreateStagingSurfaceData

[in] A pointer to a <a href="display.d3dkmdt_stagingsurfacedata">D3DKMDT_STAGINGSURFACEDATA</a> structure, if <b>StandardAllocationType</b> specifies D3DKMDT_STANDARDALLOCATION_STAGINGSURFACE.

### -field pCreateGdiSurfaceData

[in] A pointer to a <a href="display.d3dkmdt_gdisurfacedata">D3DKMDT_GDISURFACEDATA</a> structure, only available if <b>StandardAllocationType</b> specifies D3DKMDT_STANDARDALLOCATION_GDISURFACE.
This member is available beginning with Windows 7.

### -field pAllocationPrivateDriverData

[in/out] A pointer to a block of allocation private data that describes the standard allocation type; otherwise, this member is <b>NULL</b>. The allocation private data that the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md">DxgkDdiGetStandardAllocationDriverData</a> function returns depends on the type that the driver requests in <b>StandardAllocationType</b>.

### -field AllocationPrivateDriverDataSize

[out] The size, in bytes, of the allocation private data that <b>pAllocationPrivateDriverData</b> points to. If the driver sets <b>pAllocationPrivateDriverData</b> to <b>NULL</b>, the driver should set <b>AllocationPrivateDriverDataSize</b> to the size of the buffer that the driver requires to describe the given standard allocation type.
If the driver does not use private data for each allocation for standard allocations types, the driver can set <b>AllocationPrivateDriverDataSize</b> to zero. 

### -field pResourcePrivateDriverData

[in/out] A pointer to a block of resource private data that describes the standard allocation type; otherwise, this member is <b>NULL</b>. The resource private data that the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md">DxgkDdiGetStandardAllocationDriverData</a> function returns depends on the type that the driver requests in <b>StandardAllocationType</b>.

### -field ResourcePrivateDriverDataSize

[out] The size, in bytes, of the resource private data that <b>pResourcePrivateDriverData</b> points to. If the driver sets <b>pResourcePrivateDriverData</b> to <b>NULL</b>, the driver should set <b>ResourcePrivateDriverDataSize</b> to the size of the buffer that the driver requires to describe the given standard allocation type.
If the driver does not use private data for each resource for standard allocations types, the driver can set <b>ResourcePrivateDriverDataSize</b> to zero. 

## -remarks
If the display miniport driver returns <b>NULL</b> in the <b>pAllocationPrivateDriverData</b> and <b>pResourcePrivateDriverData</b> members, the driver should return the sizes of the buffers that the driver requires in the <b>AllocationPrivateDriverDataSize</b> and <b>ResourcePrivateDriverDataSize</b> members. However, the driver should not change the contents of the standard allocation structure in the union that DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA contains to obtain the required sizes of the buffers. 

Although the driver can set <b>ResourcePrivateDriverDataSize</b> or <b>AllocationPrivateDriverDataSize</b> to zero, the driver cannot set both to zero.

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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmdt_gdisurfacedata">D3DKMDT_GDISURFACEDATA</a>
</dt>
<dt>
<a href="display.d3dkmdt_shadowsurfacedata">D3DKMDT_SHADOWSURFACEDATA</a>
</dt>
<dt>
<a href="display.d3dkmdt_sharedprimarysurfacedata">D3DKMDT_SHAREDPRIMARYSURFACEDATA</a>
</dt>
<dt>
<a href="display.d3dkmdt_stagingsurfacedata">D3DKMDT_STAGINGSURFACEDATA</a>
</dt>
<dt>
<a href="display.d3dkmdt_standardallocation_type">D3DKMDT_STANDARDALLOCATION_TYPE</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md">DxgkDdiGetStandardAllocationDriverData</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
