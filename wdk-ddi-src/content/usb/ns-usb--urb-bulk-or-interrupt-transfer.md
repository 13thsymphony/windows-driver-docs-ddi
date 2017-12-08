---
UID: NS.usb._URB_BULK_OR_INTERRUPT_TRANSFER
title: URB_BULK_OR_INTERRUPT_TRANSFER
author: windows-driver-content
description: The _URB_BULK_OR_INTERRUPT_TRANSFER structure is used by USB client drivers to send or receive data on a bulk pipe or on an interrupt pipe.
old-location: buses\_urb_bulk_or_interrupt_transfer.htm
old-project: usbref
ms.assetid: 398f50ad-4c58-4585-8fb8-c523b74793e9
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: URB_BULK_OR_INTERRUPT_TRANSFER,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: _URB_BULK_OR_INTERRUPT_TRANSFER
req.alt-loc: usb.h
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
req.iface: 
req.product: Windows 10 or later.
---

# URB_BULK_OR_INTERRUPT_TRANSFER structure



## -description
<p>The <b>_URB_BULK_OR_INTERRUPT_TRANSFER</b> structure is used by USB client drivers to send or receive data on a bulk pipe or on an interrupt pipe.</p>


## -syntax

````
struct _URB_BULK_OR_INTERRUPT_TRANSFER {
  struct URB_HEADER  Hdr;
  USBD_PIPE_HANDLE    PipeHandle;
  ULONG               TransferFlags;
  ULONG               TransferBufferLength;
  PVOID               TransferBuffer;
  PMDL                TransferBufferMDL;
  struct URB  *UrbLink;
  struct URB_HCD_AREA  hca;
};
````


## -struct-fields
<dl>

### -field Hdr

<dd>
<p>Pointer to a <a href="buses._urb_header">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_BULK_OR_INTERRUPT_TRANSFER, and <b>Hdr.Length</b> must be set to <code>sizeof(_URB_BULK_OR_INTERRUPT_TRANSFER)</code>.</p>
</dd>

### -field PipeHandle

<dd>
<p>Specifies an opaque handle to the bulk or interrupt pipe. The host controller driver returns this handle when the client driver selects the device configuration with a URB of type URB_FUNCTION_SELECT_CONFIGURATION or when the client driver changes the settings for an interface with a URB of type URB_FUNCTION_SELECT_INTERFACE.  </p>
</dd>

### -field TransferFlags

<dd>
<p>
<p>Specifies zero, one, or a combination of the following flags:</p>
</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="USBD_TRANSFER_DIRECTION_IN"></a><a id="usbd_transfer_direction_in"></a><dl>

### -field USBD_TRANSFER_DIRECTION_IN

</dl>
</td>
<td width="60%">
<p>Is set to request data from a device. To transfer data to a device, this flag must be clear. </p>
</td>
</tr>
<tr>
<td width="40%"><a id="USBD_TRANSFER_DIRECTION_OUT"></a><a id="usbd_transfer_direction_out"></a><dl>

### -field USBD_TRANSFER_DIRECTION_OUT

</dl>
</td>
<td width="60%">
<p>Is set to transfer data to a device. Setting this flag is equivalent to clearing the USBD_TRANSFER_DIRECTION_IN flag. </p>
</td>
</tr>
<tr>
<td width="40%"><a id="USBD_SHORT_TRANSFER_OK"></a><a id="usbd_short_transfer_ok"></a><dl>

### -field USBD_SHORT_TRANSFER_OK

</dl>
</td>
<td width="60%">
<p>Is set to direct the host controller not to return an error when it receives a packet from the device that is shorter than the maximum packet size for the endpoint. The maximum packet size for the endpoint is reported in the <b>wMaxPacketSize</b> member of the <a href="..\usbspec\ns-usbspec--usb-endpoint-descriptor.md">USB_ENDPOINT_DESCRIPTOR</a> structure (endpoint descriptor). When  the host controller receives a packet shorter than <b>wMaxPacketSize</b> on a bulk or an interrupt endpoint, the host controller immediately stops requesting data from the endpoint and completes the transfer.  If the USBD_SHORT_TRANSFER_OK flag is not set, the host controller completes the transfer  with an error. </p>
<p>This flag should not be set unless USBD_TRANSFER_DIRECTION_IN is also set. <p><b>Note</b>  On EHCI host controllers,  USBD_SHORT_TRANSFER_OK is ignored for bulk and interrupt endpoints.  Transfer of short packets on EHCI controllers does not result in an error condition. <p class="note">On UHCI and OHCI host controllers,   if USBD_SHORT_TRANSFER_OK is not set for a bulk or interrupt transfer, a short packet transfer halts the endpoint and an error code is returned for the transfer.  The client driver must resume the endpoint by submitting a URB_FUNCTION_SYNC_RESET_PIPE_AND_CLEAR_STALL request before submitting a transfer request to the endpoint.</p>
</p>
</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field TransferBufferLength

<dd>
<p>Specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes sent to or read from the pipe in this member.</p>
</dd>

### -field TransferBuffer

<dd>
<p>Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>. The contents of this buffer depend on the value of <b>TransferFlags</b>. If USBD_TRANSFER_DIRECTION_IN is specified this buffer will contain data read from the device on return from the host controller driver. Otherwise, this buffer contains driver-supplied data for transfer to the device.</p>
</dd>

### -field TransferBufferMDL

<dd>
<p>Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. The contents of the buffer depend on the value of <b>TransferFlags</b>. If USBD_TRANSFER_DIRECTION_IN is specified, the described buffer will contain data read from the device on return from the host controller driver. Otherwise, the buffer contains driver-supplied data for transfer to the device. This MDL must be allocated from nonpaged pool.</p>
</dd>

### -field UrbLink

<dd>
<p>Reserved. Do not use.</p>
</dd>

### -field hca

<dd>
<p>Reserved. Do not use.</p>
</dd>
</dl>

## -remarks
<p>Drivers can use the <b>UsbBuildInterruptOrBulkTransferRequest</b> service routine to format this URB. Buffers specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL </b>must be nonpageable. </p>

<p>In an <a href="..\usb\ns-usb--urb.md">URB</a>, both <b>TransferBuffer</b> and <b>TransferBufferMDL</b> parameters can be non-NULL values, at the same time. In that case, the transfer buffer and the MDL pointed to <b>TransferBuffer</b> and <b>TransferBufferMDL</b> must point to the same  buffer.</p>

<p>The USB bus driver processes this URB at DISPATCH_LEVEL.</p>

<p>The reserved members of this structure must be treated as opaque and are reserved for system use.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Usb.h (include Usb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usb\ns-usb--urb.md">URB</a>
</dt>
<dt>
<a href="buses._urb_header">_URB_HEADER</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20_URB_BULK_OR_INTERRUPT_TRANSFER structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
