---
UID: NC.d3dkmddi.DXGKDDI_OPENALLOCATIONINFO
title: DXGKDDI_OPENALLOCATIONINFO
author: windows-driver-content
description: The DxgkDdiOpenAllocation function binds non-device-specific allocations that the DxgkDdiCreateAllocation function created to allocations that are specific to the specified graphics context device.
old-location: display\dxgkddiopenallocation.htm
old-project: display
ms.assetid: 551154d7-950d-40e5-810b-8d803c1731ca
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiOpenAllocation
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

# DXGKDDI_OPENALLOCATIONINFO callback



## -description
The <i>DxgkDdiOpenAllocation</i> function binds non-device-specific allocations that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function created to allocations that are specific to the specified graphics context device.



## -prototype

````
DXGKDDI_OPENALLOCATIONINFO DxgkDdiOpenAllocation;

NTSTATUS APIENTRY DxgkDdiOpenAllocation(
  _In_ const HANDLE                 hDevice,
  _In_ const DXGKARG_OPENALLOCATION *pOpenAllocation
)
{ ... }
````


## -parameters

### -param hDevice [in]

[in] A handle to the graphics context device that the allocations are bound from. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hDevice</b> member of the <a href="display.dxgkarg_createdevice">DXGKARG_CREATEDEVICE</a> structure. 


### -param pOpenAllocation [in]

[in] A pointer to a <a href="display.dxgkarg_openallocation">DXGKARG_OPENALLOCATION</a> structure that contains information about binding allocations.


## -returns
<i>DxgkDdiOpenAllocation</i> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><i>DxgkDdiOpenAllocation</i> successfully bound allocations to the graphics context device that the <i>hDevice</i> parameter specified.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters that were passed to <i>DxgkDdiOpenAllocation</i> contained errors that prevented it from completing.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl><i>DxgkDdiOpenAllocation</i> could not allocate memory that was required for it to complete.
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>The display miniport driver is not compatible with the user-mode display driver that initiated the call to <i>DxgkDdiOpenAllocation</i> (that is, supplied private data to the display miniport driver). 

 


## -remarks
The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiOpenAllocation</i> function to bind nondevice-specific allocations that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function created to allocations that are specific to the graphics context device that the <i>hDevice</i> parameter specifies. The display miniport driver binds allocations to a device so the driver can keep track of allocation data that is specific to a device. 

The display miniport driver can bind an allocation to any device that any process (on the same graphics adapter) created and not just to a device in the creating process. 

When <i>DxgkDdiOpenAllocation</i> returns STATUS_SUCCESS, the driver sets the <b>hDeviceSpecificAllocation</b> member of the <a href="display.dxgk_openallocationinfo">DXGK_OPENALLOCATIONINFO</a> structure for each allocation to a non-NULL value. The DXGK_OPENALLOCATIONINFO structure for each allocation is an element of the array that the <b>pOpenAllocation</b> member of the <a href="display.dxgkarg_openallocation">DXGKARG_OPENALLOCATION</a> structure specifies.  

The driver can modify the allocation private driver data that is passed in the <b>pPrivateDriverData</b> member of the <a href="display.dxgk_openallocationinfo">DXGK_OPENALLOCATIONINFO</a> structure only when the allocation is created (which is indicated when the <b>Create</b> bit-field flag in the <b>Flags</b> member of the <a href="display.dxgkarg_openallocation">DXGKARG_OPENALLOCATION</a> structure is set). The driver should determine that it can only read the allocation private driver data when the allocation is opened (that is, when the <b>Create</b> bit-field flag is not set).

<i>DxgkDdiOpenAllocation</i> should be made pageable.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>
</dt>
<dt>
<a href="display.dxgk_openallocationinfo">DXGK_OPENALLOCATIONINFO</a>
</dt>
<dt>
<a href="display.dxgkarg_createdevice">DXGKARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="display.dxgkarg_openallocation">DXGKARG_OPENALLOCATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPENALLOCATIONINFO callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

