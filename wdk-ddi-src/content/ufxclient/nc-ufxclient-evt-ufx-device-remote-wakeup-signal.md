---
UID: NC.ufxclient.EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL
title: EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL
author: windows-driver-content
description: The client driver's implementation to initiate remote wake-up on the function controller.
old-location: buses\evt_ufx_device_remote_wakeup_signal.htm
old-project: usbref
ms.assetid: A1250501-DC33-4AA8-8AD7-9938ECAC8AFB
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: PFN_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL
req.alt-loc: Ufxclient.h
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

# EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL callback



## -description
<p>The client driver's implementation to initiate remote wake-up on the function controller.</p>


## -prototype

````
EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL EvtUfxDeviceRemoteWakeupSignal;

void EvtUfxDeviceRemoteWakeupSignal(
  _In_ UFXDEVICE UfxDevice
)
{ ... }

typedef EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL PFN_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL;
````


## -parameters
<dl>

### -param UfxDevice [in]

<dd>
<p>The handle to a  USB device object that the client driver received in a previous call to  the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL</i> implementation with the USB function class extension (UFX) by calling the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a> method.</p>

<p>The client driver indicates completion of this event by calling the <a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a> method.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ufxclient.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>
</dt>
<dt>
<a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL callback function%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
