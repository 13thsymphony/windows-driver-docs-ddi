---
UID: NC.ufxclient.EVT_UFX_DEVICE_ADDRESSED
title: EVT_UFX_DEVICE_ADDRESSED
author: windows-driver-content
description: The client driver's implementation to assign an address on the function controller.
old-location: buses\evt_ufx_device_addressed.htm
old-project: usbref
ms.assetid: 99120A01-4674-465A-BA75-58F1871BB820
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
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
req.alt-api: PFN_UFX_DEVICE_ADDRESSED
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
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# EVT_UFX_DEVICE_ADDRESSED callback



## -description
The client driver's implementation to assign an address on the function controller.


## -prototype

````
EVT_UFX_DEVICE_ADDRESSED EvtUfxDeviceAddressed;

void EvtUfxDeviceAddressed(
  _In_ UFXDEVICE UfxDevice,
  _In_ USHORT    DeviceAddress
)
{ ... }

typedef EVT_UFX_DEVICE_ADDRESSED PFN_UFX_DEVICE_ADDRESSED;
````


## -parameters

### -param UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="buses.ufxdevicecreate">UfxDeviceCreate</a>.

### -param DeviceAddress [in]

New USB device address to assign. 

## -returns
This callback function does not return a value.

## -remarks
The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_ADDRESSED</i> implementation with the USB function class extension (UFX) by calling the <a href="buses.ufxdevicecreate">UfxDeviceCreate</a> method.

The client driver indicates completion of this event by calling the <a href="buses.ufxdeviceeventcomplete">UfxDeviceEventComplete</a> method.

## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ufxclient.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.ufxdevicecreate">UfxDeviceCreate</a>
</dt>
<dt>
<a href="buses.ufxdeviceeventcomplete">UfxDeviceEventComplete</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UFX_DEVICE_ADDRESSED callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
