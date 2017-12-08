---
UID: NF.ks.KsInitializeDevice
title: KsInitializeDevice function
author: windows-driver-content
description: The KsInitializeDevice function is called by AVStream to initialize the AVStream device class from within KsCreateDevice.
old-location: stream\ksinitializedevice.htm
old-project: stream
ms.assetid: f33122d0-7661-454a-87f7-7b5795793376
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsInitializeDevice
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
req.alt-api: KsInitializeDevice
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
---

# KsInitializeDevice function



## -description
The<b> KsInitializeDevice </b>function is called by AVStream to initialize the AVStream device class from within <a href="stream.kscreatedevice">KsCreateDevice</a>.


## -syntax

````
NTSTATUS KsInitializeDevice(
  _In_           PDEVICE_OBJECT      FunctionalDeviceObject,
  _In_           PDEVICE_OBJECT      PhysicalDeviceObject,
  _In_           PDEVICE_OBJECT      NextDeviceObject,
  _In_opt_ const KSDEVICE_DESCRIPTOR *Descriptor
);
````


## -parameters

### -param FunctionalDeviceObject [in]

A pointer to a <a href="kernel.device_object">DEVICE_OBJECT</a> structure representing the WDM functional device object for the device being initialized. 
Normally, this is returned from an <a href="kernel.iocreatedevice">IoCreateDevice</a> call. Minidrivers calling this function directly are responsible for calling <b>IoCreateDevice</b> and attaching themselves to the device stack.

### -param PhysicalDeviceObject [in]

A pointer to a <a href="kernel.device_object">DEVICE_OBJECT</a> structure representing the WDM physical device object for the device being initialized.

### -param NextDeviceObject [in]

A pointer to the next <a href="kernel.device_object">DEVICE_OBJECT</a> structure in the device stack as determined by a call to <a href="kernel.ioattachdevicetodevicestack">IoAttachDeviceToDeviceStack</a>.

### -param Descriptor [in, optional]

A pointer to a <a href="stream.ksdevice_descriptor">KSDEVICE_DESCRIPTOR</a> structure that describes the characteristics of the device being initialized. If this parameter is <b>NULL</b>, the device is initialized with the default characteristics and has no associated filter factories.

## -returns
<b>KsInitializeDevice</b> returns STATUS_SUCCESS if the device was successfully initialized. Otherwise, it returns an appropriate error code.

## -remarks
Most minidrivers do not call this function directly. Only call <b>KsInitializeDevice</b> if your minidriver does not use <a href="stream.ksinitializedriver">KsInitializeDriver</a> for initialization, handles <b>AddDevice</b> independently, and does not use <a href="stream.ksadddevice">KsAddDevice</a> or <a href="stream.kscreatedevice">KsCreateDevice</a> in its <b>AddDevice</b> handler. 

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
<a href="stream.ksinitializedriver">KsInitializeDriver</a>
</dt>
<dt>
<a href="stream.ksadddevice">KsAddDevice</a>
</dt>
<dt>
<a href="stream.kscreatedevice">KsCreateDevice</a>
</dt>
<dt>
<a href="stream.ksterminatedevice">KsTerminateDevice</a>
</dt>
<dt>
<a href="stream.ksdevice">KSDEVICE</a>
</dt>
<dt>
<a href="kernel.iocreatedevice">IoCreateDevice</a>
</dt>
<dt>
<a href="kernel.ioattachdevicetodevicestack">IoAttachDeviceToDeviceStack</a>
</dt>
<dt>
<a href="kernel.driver_object">DRIVER_OBJECT</a>
</dt>
<dt>
<a href="kernel.device_object">DEVICE_OBJECT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsInitializeDevice function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
