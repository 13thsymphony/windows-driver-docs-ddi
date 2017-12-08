---
UID: NC.vhf.EVT_VHF_ASYNC_OPERATION
title: EVT_VHF_ASYNC_OPERATION
author: windows-driver-content
description: The HID source driver implements this event callback if it wants to support one of the four asynchronous operation to get and set HID reports.
old-location: hid\evtvhfasyncoperation.htm
old-project: hid
ms.assetid: C42174FE-202F-405D-840B-8613762F43AC
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: vhf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EvtVhfAsyncOperation
req.alt-loc: vhf.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# EVT_VHF_ASYNC_OPERATION callback



## -description
<p>The HID source driver implements this event callback if it wants to support one of the four asynchronous operation to get and set HID reports.</p>


## -prototype

````
EVT_VHF_ASYNC_OPERATION EvtVhfAsyncOperation;

void EvtVhfAsyncOperation(
  _In_     PVOID              VhfClientContext,
  _In_     VHFOPERATIONHANDLE VhfOperationHandle,
  _In_opt_ PVOID              VhfOperationContext,
  _In_     PHID_XFER_PACKET   HidTransferPacket
)
{ ... }
````


## -parameters
<dl>

### -param VhfClientContext [in]

<dd>
<p>An opaque pointer to a HID source driver-defined buffer that the driver passed in the <a href="..\vhf\ns-vhf--vhf-config.md">VHF_CONFIG</a> structure supplied to <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a> to create the virtual HID device.</p>
</dd>

### -param VhfOperationHandle [in]

<dd>
<p>An opaque handle that uniquely identifies this asynchronous operation. </p>
</dd>

### -param VhfOperationContext [in, optional]

<dd>
<p>Pointer to a buffer that can be used by the HID source driver for servicing the operation. Size of the buffer is specified by the HID source driver in the <a href="..\vhf\ns-vhf--vhf-config.md">VHF_CONFIG</a> structure supplied to <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a>.</p>
</dd>

### -param HidTransferPacket [in]

<dd>
<p>A pointer to a <a href="..\hidclass\ns-hidclass--hid-xfer-packet.md">HID_XFER_PACKET</a> structure. Contains information about a HID Report and is used by the HID source driver and the HID class/mini driver pair for I/O requests to get or set a report.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>There are four types of asynchronous operations that your HID source driver can support: <b>GetFeature</b>, <b>SetFeature</b>, <b>WriteReport</b>, <b>GetInputReport</b>. </p>

<p>To support such an operation, the HID source driver must implement an <i>EvtVhfAsyncOperation</i> callback function and register it with the Virtual HID Framework (VHF) in the driver's call to <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a> function after calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.  For example, for <b>GetFeature</b>, the driver must implement  <i>EvtVhfAsyncOperation</i> and set the <b>EvtVhfAsyncOperationGetFeature</b> member of the <a href="..\vhf\ns-vhf--vhf-config.md">VHF_CONFIG</a> to a function pointer of the implemented function.</p>

<p>When VHF gets a request that sets or queries a HID Report, VHF invokes the previously-registered <i>EvtVhfAsyncOperation</i> callback function and an asynchronous operation starts. Each operation is identified by a VHFOPERATIONHANDLE handle that is set by VHF. If the driver specified a non-zero value in the <b>OperationContextSize</b> member of the <a href="..\vhf\ns-vhf--vhf-config.md">VHF_CONFIG</a> during initialization, VHF allocates a buffer of that size and passes a pointer to that buffer  in the <i>VhfOperationContext</i> parameter when it invokes  <i>EvtVhfAsyncOperation</i>. </p>

<p><i>HidTransferPacket</i> is the transfer buffer for this operation that points to a VHF-allocated structure containing HID Report-specific details. For example, if the operation is <b>GetFeature</b>, upon completion the buffer is filled by  the HID source driver with the requested HID Feature Report.</p>

<p>When the operation is complete, HID source calls <a href="..\vhf\nf-vhf-vhfasyncoperationcomplete.md">VhfAsyncOperationComplete</a> to report the completion status.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>None supported</p>
</td>
</tr>
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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Vhf.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20EVT_VHF_ASYNC_OPERATION callback function%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
