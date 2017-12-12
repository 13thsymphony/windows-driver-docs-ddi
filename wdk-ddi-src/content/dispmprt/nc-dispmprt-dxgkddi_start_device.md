---
UID: NC.dispmprt.DXGKDDI_START_DEVICE
title: DXGKDDI_START_DEVICE
author: windows-driver-content
description: The DxgkDdiStartDevice function prepares a display adapter to receive I/O requests.
old-location: display\dxgkddistartdevice.htm
old-project: display
ms.assetid: ffacbb39-2581-4207-841d-28ce57fbc64d
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SYMBOL_INFO_EX, *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiStartDevice
req.alt-loc: dispmprt.h
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

# DXGKDDI_START_DEVICE callback



## -description
The <i>DxgkDdiStartDevice</i> function prepares a display adapter to receive I/O requests.



## -prototype

````
DXGKDDI_START_DEVICE DxgkDdiStartDevice;

NTSTATUS DxgkDdiStartDevice(
  _In_  const PVOID              MiniportDeviceContext,
  _In_        PDXGK_START_INFO   DxgkStartInfo,
  _In_        PDXGKRNL_INTERFACE DxgkInterface,
  _Out_       PULONG             NumberOfVideoPresentSources,
  _Out_       PULONG             NumberOfChildren
)
{ ... }
````


## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param DxgkStartInfo [in]

A pointer to a <a href="display.dxgk_start_info">DXGK_START_INFO</a> structure that contains information that the display miniport driver needs for initialization. 


### -param DxgkInterface [in]

A pointer to a <a href="display.dxgkrnl_interface2">DXGKRNL_INTERFACE</a> structure that contains pointers to functions, implemented by the DirectX graphics kernel subsystem, that the display miniport driver can call. 


### -param NumberOfVideoPresentSources [out]

A pointer to a <b>ULONG</b> variable that receives the number of video present sources supported by the display adapter. For more information about video present sources, see <a href="https://msdn.microsoft.com/27687fa4-1266-4341-b68a-83374c24ef73">Multiple Monitors and Video Present Networks</a>.


### -param NumberOfChildren [out]

A pointer to a <b>ULONG</b> variable that receives the total number of devices that are children of the display adapter represented by <i>MiniportDeviceContext</i>. This count must include potential child devices as well as child devices that are currently present. For example, if docking a portable computer will make additional video outputs available, those video outputs must be counted regardless of whether the portable computer is currently docked. For more information about child devices, see <a href="https://msdn.microsoft.com/9fd20e1a-db98-4571-8fc4-6d33fd0e2f16">Child Devices of the Display Adapter</a>.


## -returns
<i>DxgkDdiStartDevice</i> returns <b>STATUS_SUCCESS</b> if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.


## -remarks
The <i>DxgkDdiStartDevice</i> function must perform the following actions:

Save the function pointers supplied by the <a href="display.dxgkrnl_interface2">DXGKRNL_INTERFACE</a> structure passed to the <i>DxgkInterface</i> parameter. Also save the <b>DeviceHandle</b> member of the <b>DXGKRNL_INTERFACE</b> structure; you will need that handle to call back into the DirectX graphics kernel subsystem.

Allocate a <a href="display.dxgk_device_info">DXGK_DEVICE_INFO</a> structure, and call <a href="..\dispmprt\nc-dispmprt-dxgkcb_get_device_information.md">DxgkCbGetDeviceInformation</a> to fill in the members of that structure, which include the registry path, the PDO, and a list of translated resources for the display adapter represented by <i>MiniportDeviceContext</i>. Save selected members (ones that the display miniport driver will need later) of the <b>DXGK_DEVICE_INFO</b> structure in the context block represented by <i>MiniportDeviceContext.</i>

Map memory resources into system space by calling the <a href="..\dispmprt\nc-dispmprt-dxgkcb_map_memory.md">DxgkCbMapMemory</a> function.

Initialize the context block represented by <i>MiniportDeviceContext</i> with any state that is required to prepare the hardware to receive I/O requests.

Set <i>NumberOfVideoPresentSources </i> to the number of video present sources supported by the display adapter that is represented by <i>MiniportDeviceContext</i>.

Set <i>NumberOfChildren </i> to the number of devices that are (or could become) children of the display adapter represented by <i>MiniportDeviceContext</i>.

Enable interrupts for the display adapter represented by <i>MiniportDeviceContext</i>.

Starting with Windows Display Driver Model (WDDM) 1.2, the display miniport driver calls   the <a href="display.DxgkCbAcquirePostDisplayOwnership">DxgkCbAcquirePostDisplayOwnership</a> function to obtain the information about the display mode that had been previously set by the firmware and system loader. If <b>DxgkCbAcquirePostDisplayOwnership</b> returns with <b>STATUS_SUCCESS</b>, the driver determines whether it has to reinitialize the display based on the display mode information that was returned through the <i>DisplayInfo</i> parameter. Otherwise,  the driver should not assume that any specific display mode is currently enabled on the device, and it should initialize the display.

The <i>DxgkDdiStartDevice</i> function should be made pageable.


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
Available starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dispmprt.h</dt>
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
<a href="display.dxgk_device_info">DXGK_DEVICE_INFO</a>
</dt>
<dt>
<a href="display.DxgkCbAcquirePostDisplayOwnership">DxgkCbAcquirePostDisplayOwnership</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb_get_device_information.md">DxgkCbGetDeviceInformation</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb_map_memory.md">DxgkCbMapMemory</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device.md">DxgkDdiStopDevice</a>
</dt>
<dt>
<a href="display.dxgkrnl_interface2">DXGKRNL_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_START_DEVICE callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

