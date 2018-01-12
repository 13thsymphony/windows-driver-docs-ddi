---
UID: NF:ks.KsCreateDevice
title: KsCreateDevice function
author: windows-driver-content
description: The KsCreateDevice function creates an AVStream device.
old-location: stream\kscreatedevice.htm
old-project: stream
ms.assetid: 92a1c2d7-6a6f-4b5e-be04-b444abe3e1d5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsCreateDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsCreateDevice
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: 
---

# KsCreateDevice function



## -description
The<b> KsCreateDevice </b>function creates an AVStream device.



## -syntax

````
NTSTATUS KsCreateDevice(
  _In_            PDRIVER_OBJECT      DriverObject,
  _In_            PDEVICE_OBJECT      PhysicalDeviceObject,
  _In_opt_  const KSDEVICE_DESCRIPTOR *Descriptor,
  _In_            ULONG               ExtensionSize,
  _Out_opt_       PKSDEVICE           *Device
);
````


## -parameters

### -param DriverObject [in]

A pointer to the WDM driver object of the minidriver.


### -param PhysicalDeviceObject [in]

A pointer to the WDM physical device object for the device you want to create under AVStream.


### -param Descriptor [in, optional]

A pointer to a device descriptor that describes the characteristics of the device being created. If the caller does not specify this optional parameter, AVStream creates a device with default characteristics and no associated filter factories.


### -param ExtensionSize [in]

This parameter contains the size of the device extension. If this is zero, the default extension size is used. If not, it must be at least sizeof (KSDEVICE_HEADER).


### -param Device [out, optional]

A pointer to a memory location that contains the address of the created <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure. Optional.


## -returns
Returns STATUS_SUCCESS if the device is created successfully. Otherwise, it returns an appropriate error code.


## -remarks
Normally, the minidriver does not call this function directly. Instead, <b>KsCreateDevice</b> is called by the default <i>AddDevice</i> handler, <a href="..\ks\nf-ks-ksadddevice.md">KsAddDevice</a>. Because <b>KsAddDevice</b> makes an internal call to <b>KsCreateDevice</b>, drivers that call <b>KsCreateDevice</b> should not call <b>KsAddDevice</b> separately.

A minidriver that calls <b>KsCreateDevice</b> directly should not use <a href="..\ks\nf-ks-ksinitializedriver.md">KsInitializeDriver</a>. If the minidriver is not calling <b>KsInitializeDriver</b>, it should instead provide its own <i>AddDevice</i> callback. The minidriver can then call <b>KsCreateDevice</b> from that <i>AddDevice</i> callback. 

If no <a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a> is provided, AVStream creates a device with the default characteristics and no associated filter factories. If a KSDEVICE_DESCRIPTOR is supplied and contains a <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> table with a create dispatch, the create dispatch is called. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
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
<a href="..\ks\nf-ks-ksadddevice.md">KsAddDevice</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksinitializedevice.md">KsInitializeDevice</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksinitializedriver.md">KsInitializeDriver</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCreateDevice function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

