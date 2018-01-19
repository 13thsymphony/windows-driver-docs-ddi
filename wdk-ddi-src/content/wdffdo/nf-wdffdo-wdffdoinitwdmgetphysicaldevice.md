---
UID : NF:wdffdo.WdfFdoInitWdmGetPhysicalDevice
title : WdfFdoInitWdmGetPhysicalDevice function
author : windows-driver-content
description : The WdfFdoInitWdmGetPhysicalDevice method retrieves a device's WDM physical device object (PDO).
old-location : wdf\wdffdoinitwdmgetphysicaldevice.htm
old-project : wdf
ms.assetid : eba64244-50ff-4c59-a30f-46874c683e63
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfFdoInitWdmGetPhysicalDevice
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdffdo.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.alt-api : WdfFdoInitWdmGetPhysicalDevice
req.alt-loc : Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance : DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product : Windows 10 or later.
---


# WdfFdoInitWdmGetPhysicalDevice function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoInitWdmGetPhysicalDevice</b> method retrieves a device's WDM physical device object (PDO).

## Syntax

````
PDEVICE_OBJECT WdfFdoInitWdmGetPhysicalDevice(
  _In_ PWDFDEVICE_INIT DeviceInit
);
````

## Parameters

`DeviceInit`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.


## Return Value

If the operation succeeds, the method returns a pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. Otherwise the method returns <b>NULL</b>.

## Remarks

The driver must call <b>WdfFdoInitWdmGetPhysicalDevice</b> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about the <b>WdfFdoInitWdmGetPhysicalDevice</b> method, see <a href="https://msdn.microsoft.com/3b988f6d-c50e-412d-85cb-031746535ff4">Creating Device Objects in a Function Driver</a>.

The following code example obtains a pointer to a DEVICE_OBJECT structure that represents a device's WDM PDO.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdffdo.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2 |