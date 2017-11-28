---
UID: NC.d3dkmddi.DXGKCB_GETHANDLEDATA
title: DXGKCB_GETHANDLEDATA
author: windows-driver-content
description: The DxgkCbGetHandleData function retrieves the private data that is associated with an allocation.
old-location: display\dxgkcbgethandledata.htm
old-project: display
ms.assetid: 144429e5-34e6-4416-980e-2838e8f9e415
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbGetHandleData
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
req.irql: < DISPATCH_LEVEL
req.iface: 
---

# DXGKCB_GETHANDLEDATA callback



## -description
<p>The <i>DxgkCbGetHandleData</i> function retrieves the private data that is associated with an allocation.</p>


## -prototype

````
DXGKCB_GETHANDLEDATA DxgkCbGetHandleData;

VOID* APIENTRY CALLBACK DxgkCbGetHandleData(
  _In_ const DXGKARGCB_GETHANDLEDATA *pData
)
{ ... }
````


## -parameters
<dl>

### -param <i>pData</i> [in]

<dd>
<p>[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557534">DXGKARGCB_GETHANDLEDATA</a> structure that describes the allocation data to retrieve.</p>
</dd>
</dl>

## -returns
<p><i>DxgkCbGetHandleData</i> returns a buffer that contains the private data for the allocation.</p>

<p>If <i>DxgkCbGetHandleData</i> returns a <b>NULL</b> pointer, the Microsoft DirectX graphics kernel subsystem was unable to resolve the handle that is supplied in the <b>hObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557534">DXGKARGCB_GETHANDLEDATA</a> structure to private data because, for example, of the following possible reasons: </p>

<p>If a <b>NULL</b> pointer is returned, the display miniport driver should fail its currently running DDI function with STATUS_INVALID_HANDLE.</p>

## -remarks
<p>When the DirectX graphics kernel subsystem calls the display miniport driver's <a href="display.dxgkddicreateallocation">DxgkDdiCreateAllocation</a> function to create handles to allocations, the display miniport driver can create private data for each allocation handle. The display miniport driver can subsequently call the <b>DxgkCbGetHandleData</b> function to retrieve private data for each graphics subsystem-specific handle. Therefore, the display miniport driver is not required to maintain a private allocation handle table. </p>

<p>If the <b>DeviceSpecific</b> bit-field flag is set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557534">DXGKARGCB_GETHANDLEDATA</a> structure that <i>pData</i> points to, <b>DxgkCbGetHandleData</b> returns the device-specific data that is associated with the device-specific handle that the driver returned from the call to its <a href="display.dxgkddiopenallocation">DxgkDdiOpenAllocation</a> function. Note that the <b>DeviceSpecific</b> bit-field flag is valid only if the display miniport driver also sets the <b>Type</b> member of DXGKARGCB_GETHANDLEDATA to the DXGK_HANDLE_ALLOCATION enumeration value for the handle in the <b>hObject</b> member of DXGKARGCB_GETHANDLEDATA.</p>

<p>The following code example shows an implementation of <a href="display.dxgkddiopenallocation">DxgkDdiOpenAllocation</a> in which <b>DxgkCbGetHandleData</b> is called.</p>

<p>When the DirectX graphics kernel subsystem calls the display miniport driver's <a href="display.dxgkddicreateallocation">DxgkDdiCreateAllocation</a> function to create handles to allocations, the display miniport driver can create private data for each allocation handle. The display miniport driver can subsequently call the <b>DxgkCbGetHandleData</b> function to retrieve private data for each graphics subsystem-specific handle. Therefore, the display miniport driver is not required to maintain a private allocation handle table. </p>

<p>If the <b>DeviceSpecific</b> bit-field flag is set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557534">DXGKARGCB_GETHANDLEDATA</a> structure that <i>pData</i> points to, <b>DxgkCbGetHandleData</b> returns the device-specific data that is associated with the device-specific handle that the driver returned from the call to its <a href="display.dxgkddiopenallocation">DxgkDdiOpenAllocation</a> function. Note that the <b>DeviceSpecific</b> bit-field flag is valid only if the display miniport driver also sets the <b>Type</b> member of DXGKARGCB_GETHANDLEDATA to the DXGK_HANDLE_ALLOCATION enumeration value for the handle in the <b>hObject</b> member of DXGKARGCB_GETHANDLEDATA.</p>

<p>The following code example shows an implementation of <a href="display.dxgkddiopenallocation">DxgkDdiOpenAllocation</a> in which <b>DxgkCbGetHandleData</b> is called.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt; DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557534">DXGKARGCB_GETHANDLEDATA</a>
</dt>
<dt>
<a href="display.dxgkddicreateallocation">DxgkDdiCreateAllocation</a>
</dt>
<dt>
<a href="display.dxgkddiopenallocation">DxgkDdiOpenAllocation</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_GETHANDLEDATA callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
