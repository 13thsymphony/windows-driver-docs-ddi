---
UID: NF:ks.KsInitializeDevice
title: KsInitializeDevice function
author: windows-driver-content
description: The KsInitializeDevice function is called by AVStream to initialize the AVStream device class from within KsCreateDevice.
old-location: stream\ksinitializedevice.htm
old-project: stream
ms.assetid: f33122d0-7661-454a-87f7-7b5795793376
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksinitializedevice, KsInitializeDevice, avfunc_dfdb87f8-ade9-4ba6-87a3-440e9abb80b4.xml, ks/KsInitializeDevice, KsInitializeDevice function [Streaming Media Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsInitializeDevice
product: Windows
targetos: Windows
req.typenames: 
---


# KsInitializeDevice function
The<b> KsInitializeDevice </b>function is called by AVStream to initialize the AVStream device class from within <a href="..\ks\nf-ks-kscreatedevice.md">KsCreateDevice</a>.

## Syntax

````
NTSTATUS KsInitializeDevice(
  _In_           PDEVICE_OBJECT      FunctionalDeviceObject,
  _In_           PDEVICE_OBJECT      PhysicalDeviceObject,
  _In_           PDEVICE_OBJECT      NextDeviceObject,
  _In_opt_ const KSDEVICE_DESCRIPTOR *Descriptor
);
````

## Parameters

`FunctionalDeviceObject`

A pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure representing the WDM functional device object for the device being initialized. 

Normally, this is returned from an <a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a> call. Minidrivers calling this function directly are responsible for calling <b>IoCreateDevice</b> and attaching themselves to the device stack.

`PhysicalDeviceObject`

A pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure representing the WDM physical device object for the device being initialized.

`NextDeviceObject`

A pointer to the next <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure in the device stack as determined by a call to <a href="..\wdm\nf-wdm-ioattachdevicetodevicestack.md">IoAttachDeviceToDeviceStack</a>.

`Descriptor`

A pointer to a <a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a> structure that describes the characteristics of the device being initialized. If this parameter is <b>NULL</b>, the device is initialized with the default characteristics and has no associated filter factories.


## Return Value

<b>KsInitializeDevice</b> returns STATUS_SUCCESS if the device was successfully initialized. Otherwise, it returns an appropriate error code.

## Remarks

Most minidrivers do not call this function directly. Only call <b>KsInitializeDevice</b> if your minidriver does not use <a href="..\ks\nf-ks-ksinitializedriver.md">KsInitializeDriver</a> for initialization, handles <b>AddDevice</b> independently, and does not use <a href="..\ks\nf-ks-ksadddevice.md">KsAddDevice</a> or <a href="..\ks\nf-ks-kscreatedevice.md">KsCreateDevice</a> in its <b>AddDevice</b> handler.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\nf-ks-kscreatedevice.md">KsCreateDevice</a>

<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>

<a href="..\ks\nf-ks-ksterminatedevice.md">KsTerminateDevice</a>

<a href="..\ks\nf-ks-ksinitializedriver.md">KsInitializeDriver</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>

<a href="..\wdm\nf-wdm-ioattachdevicetodevicestack.md">IoAttachDeviceToDeviceStack</a>

<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>

<a href="..\ks\nf-ks-ksadddevice.md">KsAddDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsInitializeDevice function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>