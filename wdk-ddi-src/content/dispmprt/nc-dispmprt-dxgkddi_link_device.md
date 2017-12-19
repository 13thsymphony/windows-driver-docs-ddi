---
UID: NC.dispmprt.DXGKDDI_LINK_DEVICE
title: DXGKDDI_LINK_DEVICE
author: windows-driver-content
description: The optional DxgkDdiLinkDevice function queries the display miniport driver for information on the linked adapter configuration.
old-location: display\dxgkddilinkdevice.htm
old-project: display
ms.assetid: fb9b7c58-1c4f-42e4-a59f-4a529d3caca2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SYMBOL_INFO_EX, SYMBOL_INFO_EX, PSYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiLinkDevice
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

# DXGKDDI_LINK_DEVICE callback



## -description
The optional <i>DxgkDdiLinkDevice</i> function queries the display miniport driver for information on the linked adapter configuration. 



## -prototype

````
DXGKDDI_LINK_DEVICE DxgkDdiLinkDevice;

NTSTATUS DxgkDdiLinkDevice(
  _In_    const PDEVICE_OBJECT PhysicalDeviceObject,
  _In_    const PVOID          MiniportDeviceContext,
  _Inout_       PLINKED_DEVICE LinkedDevice
)
{ ... }
````


## -parameters

### -param PhysicalDeviceObject [in]

A pointer to a physical device object (PDO) that identifies a display adapter.


### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.


### -param LinkedDevice [in, out]

A pointer to a <a href="display.linked_device">LINKED_DEVICE</a> structure that contains information on the linked display adapter configuration.


## -returns
<i>DxgkDdiLinkDevice</i> returns STATUS_SUCCESS, or an appropriate error code if information on the linked adapter configuration cannot be obtained.


## -remarks
The <i>DxgkDdiLinkDevice</i> function should be implemented by drivers of display adapters that support linked display adapters.

If this function is provided, the operating system will query the display miniport driver for the linked adapter configuration immediately after a call is made to <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>.

If the operating system does not enumerate all the expected display adapters in the structure pointed to by <i>LinkedDevice</i>, the system will start in VGA mode.

The driver can enumerate only one leading link in the chain of linked display adapters.

Plug and Play or power events cause the leading linked adapter to power up or start after the remaining linked adapters, or, conversely, such events cause the leading linked adapter to power down or to be disabled before the remaining linked adapters.


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
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="display.linked_device">LINKED_DEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_LINK_DEVICE callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

