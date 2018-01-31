---
UID : NF:ks.KsInitializeDriver
title : KsInitializeDriver function
author : windows-driver-content
description : The KsInitializeDriver function initializes the driver object of an AVStream minidriver.
old-location : stream\ksinitializedriver.htm
old-project : stream
ms.assetid : 5a77e59f-ce64-4ff2-ac95-c9062cef20d2
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsInitializeDriver, stream.ksinitializedriver, KsInitializeDriver function [Streaming Media Devices], avfunc_2a16bc8c-a92a-4792-8007-29735a19f806.xml, ks/KsInitializeDriver
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---


# KsInitializeDriver function
The<b> KsInitializeDriver </b>function initializes the driver object of an AVStream minidriver.

## Syntax

````
NTSTATUS KsInitializeDriver(
  _In_           PDRIVER_OBJECT      DriverObject,
  _In_           PUNICODE_STRING     RegistryPath,
  _In_opt_ const KSDEVICE_DESCRIPTOR *Descriptor
);
````

## Parameters

`DriverObject`

A pointer to the <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure for the AVStream driver being initialized. Minidrivers that call <b>KsInitializeDriver</b> should use the driver object passed to <b>DriverEntry</b> by the operating system.

`RegistryPathName`

TBD

`Descriptor`

A pointer to a <a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a> structure that specifies the characteristics of the device being initialized. If this pointer is <b>NULL</b>, a device is created with default characteristics and no associated filter factories.


## Return Value

<b>KsInitializeDriver</b> returns STATUS_SUCCESS or an appropriate error code as returned by <a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a> or internal AVStream device initialization routines.

## Remarks

This function is typically called from <b>DriverEntry</b>. If the minidriver passes in a device descriptor, AVStream creates a device with the specified characteristics at <b>AddDevice</b> time. Minidrivers that perform device initialization themselves do not necessarily need to call <b>KsInitializeDriver</b>.  For more information, see <a href="https://msdn.microsoft.com/666d6efb-93ec-43f3-87c5-ea1a3983bfd0">Initializing an AVStream Minidriver</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558721">DriverEntry of AVStream</a>

<a href="..\ks\nf-ks-ksinitializedevice.md">KsInitializeDevice</a>

<a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a>

<a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a>

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>

<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>

<a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsInitializeDriver function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>