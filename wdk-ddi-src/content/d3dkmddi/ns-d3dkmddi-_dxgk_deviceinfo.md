---
UID: NS.D3DKMDDI._DXGK_DEVICEINFO
title: _DXGK_DEVICEINFO
author: windows-driver-content
description: The DXGK_DEVICEINFO structure describes parameters that the Microsoft DirectX graphics kernel subsystem requires from the display miniport driver.
old-location: display\dxgk_deviceinfo.htm
old-project: display
ms.assetid: 8d941bee-2473-43f8-a157-002708b247aa
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_DEVICEINFO, DXGK_DEVICEINFO
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
req.alt-api: DXGK_DEVICEINFO
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

# _DXGK_DEVICEINFO structure



## -description
The DXGK_DEVICEINFO structure describes parameters that the Microsoft DirectX graphics kernel subsystem requires from the display miniport driver.



## -syntax

````
typedef struct _DXGK_DEVICEINFO {
  UINT                 DmaBufferSize;
  UINT                 DmaBufferSegmentSet;
  UINT                 DmaBufferPrivateDataSize;
  UINT                 AllocationListSize;
  UINT                 PatchLocationListSize;
  DXGK_DEVICEINFOFLAGS Flags;
} DXGK_DEVICEINFO;
````


## -struct-fields

### -field DmaBufferSize

[out] The size, in bytes, of the buffer of hardware commands that is sent through direct memory access (DMA) to the hardware.

The DMA buffer can grow and shrink after the device is created; however, the DMA buffer can never shrink smaller than the starting size that <b>DmaBufferSize</b> specifies. 


### -field DmaBufferSegmentSet

[out] The identifiers of the segments where the DMA buffers should be made accessible to the graphics processing unit (GPU). 


### -field DmaBufferPrivateDataSize

[out] The size, in bytes, of the driver-resident private data structure that is associated with each DMA buffer. Memory for this private data structure is allocated from nonpaged pool. If the driver specifies zero in <b>DmaBufferPrivateDataSize</b>, no memory is allocated for the private data structure.

The private data structure that is associated with a DMA buffer is initialized to zero when the DMA buffer is created. During the lifetime of the DMA buffer, the video memory manager never accesses the private data structure that is associated with the DMA buffer.


### -field AllocationListSize

[out] The starting number of elements in an array of allocations (that is, an array of <a href="display.dxgk_allocationlist">DXGK_ALLOCATIONLIST</a> structures). This number is the starting number of allocations that the driver requests to be in the <b>pAllocationList</b> members of <a href="display.dxgkarg_present">DXGKARG_PRESENT</a> and <a href="display.dxgkarg_render">DXGKARG_RENDER</a> structures in calls to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> and <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a> functions. 

The allocation list can grow and shrink after the device is created; however, the allocation list can never shrink smaller than the starting size that <b>AllocationListSize</b> specifies. 


### -field PatchLocationListSize

[out] The starting number of elements in an array of patch locations (that is, an array of <a href="display.d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a> structures) for the device in user mode and kernel mode. This number is the starting number of patch locations that the driver requests to be in the <b>pPatchLocationListIn</b> members of <a href="display.dxgkarg_render">DXGKARG_RENDER</a> structures in calls to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a> function. 

The patch-location list can grow and shrink after the device is created; however, the patch-location list can never shrink smaller than the starting size that <b>PatchLocationListSize</b> specifies. 


### -field Flags

[out] A <a href="display.dxgk_deviceinfoflags">DXGK_DEVICEINFOFLAGS</a> structure that identifies, in bit-field flags, information about the device.


## -remarks
The display miniport driver specifies values for the <b>DmaBufferSize</b> and <b>AllocationListSize</b> members to guarantee the following:

The DirectX graphics subsystem can use only one DMA buffer to display (by using the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> function) at least one <a href="display.rect">RECT</a> structure for all scenarios.

The sizes of DMA and allocation-list buffers are large enough to hold at least one command that cannot be split across multiple buffers.

The sizes of DMA and allocation-list buffers are large enough to avoid setup and DMA overhead. 

The display miniport driver can specify only aperture segments in the <b>DmaBufferSegmentSet</b> member; if the driver specifies a memory segment, a device-creation failure occurs. 

If the driver sets <b>DmaBufferSegmentSet</b> to 0, the video memory manager allocates contiguous paged-locked memory, which is mapped write-combined memory, for the DMA buffers. Therefore, the GPU must access DMA buffers by using PCI cycles on systems where AGP transfers that occur outside the AGP aperture are not permitted.


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
<a href="display.d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a>
</dt>
<dt>
<a href="display.dxgk_allocationlist">DXGK_ALLOCATIONLIST</a>
</dt>
<dt>
<a href="display.dxgk_deviceinfoflags">DXGK_DEVICEINFOFLAGS</a>
</dt>
<dt>
<a href="display.dxgkarg_present">DXGKARG_PRESENT</a>
</dt>
<dt>
<a href="display.dxgkarg_render">DXGKARG_RENDER</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_DEVICEINFO structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

