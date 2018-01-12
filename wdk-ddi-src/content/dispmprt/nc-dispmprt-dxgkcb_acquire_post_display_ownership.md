---
UID: NC:dispmprt.DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP
title: DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP
author: windows-driver-content
description: Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to obtain the display information from the current power-on self-test (POST) display device or the previously running WDDM driver.
old-location: display\DxgkCbAcquirePostDisplayOwnership.htm
old-project: display
ms.assetid: 6454adb3-c958-467b-acbc-b8937b98cd57
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SYMBOL_INFO_EX, *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbAcquirePostDisplayOwnership
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
req.irql: <= APC_LEVEL
req.typenames: *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
---

# DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP callback



## -description
Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to obtain the display information from the current  power-on self-test (POST) display device or the previously running WDDM driver.

 The driver must use this display information to optimize the initial mode change request after the display device has been started.



## -prototype

````
DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP DxgkCbAcquirePostDisplayOwnership;

NTSTATUS APIENTRY* DxgkCbAcquirePostDisplayOwnership(
  _In_  HANDLE                   DeviceHandle,
  _Out_ DXGK_DISPLAY_INFORMATION *DisplayInfo
)
{ ... }
````


## -parameters

### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.


### -param DisplayInfo [out]

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_display_information.md">DXGK_DISPLAY_INFORMATION</a> structure that is allocated by the display miniport driver. If <i>DxgkCbAcquirePostDisplayOwnership</i> returns STATUS_SUCCESS, this structure contains display information for the current display device that is used for POST operations.


## -returns
<i>DxgkCbAcquirePostDisplayOwnership</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.


## -remarks
The <i>DisplayInfo</i>-&gt;<b>ColorFormat</b> member must include a bitwise-OR combination of the following two formats:

If the operating system reports back the <b>D3DDDIFMT_R8G8B8</b> format, the display miniport driver should ignore it.

It is possible that the <i>DisplayInfo</i>-&gt;<b>TargetId</b> member is not initialized. In this case, the identifier of the video present target is <b>D3DDDI_ID_UNINITIALIZED</b>. Typically, this occurs after a system boot.

Similarly, it is possible that the <i>DisplayInfo</i>-&gt;<b>AcpiId</b> member is not initialized. In this case, the ACPI identifier <b>AcpiId</b> has a value of zero.

In the case of a driver-to-driver upgrade, the previous driver will have provided the target identifier and the ACPI identifier.

Starting with WDDM 1.2, the display miniport driver must follow these guidelines when it calls <i>DxgkCbAcquirePostDisplayOwnership</i>:

The entry point for the <i>DxgkCbAcquirePostDisplayOwnership</i> function is part of the <a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a> structure. This structure is returned to the driver through the  <i>DxgkInterface</i> parameter when the driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function is called.

	It is optional for the display miniport driver to call <i>DxgkCbAcquirePostDisplayOwnership</i>. However, the operating system might still call the <a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a> function of the device driver if the driver did not previously call <i>DxgkCbAcquirePostDisplayOwnership</i>.

The display miniport driver must only call the <i>DxgkCbAcquirePostDisplayOwnership</i> function if the driver is running under Windows 8 or a later version of the Windows operating system.

<i>DxgkCbAcquirePostDisplayOwnership</i> may return a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_display_information.md">DXGK_DISPLAY_INFORMATION</a> structure with the <b>Width</b> member set to zero. This indicates that either the  current display device is not capable of POST operations or the operating system does not have the current display information for the current POST device.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
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
Header

</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_display_information.md">DXGK_DISPLAY_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_set_power_state.md">DxgkDdiSetPowerState</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlgetversion.md">RtlGetVersion</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

