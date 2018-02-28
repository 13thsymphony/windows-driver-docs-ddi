---
UID: NC:pcivirt.SRIOV_GET_DEVICE_LOCATION
title: SRIOV_GET_DEVICE_LOCATION
author: windows-driver-content
description: Retrieves information about the current location of the PCI device on the bus, such as PCI Segment, Bus, Device and Function number.
old-location: pci\sriov_get_device_location.htm
old-project: PCI
ms.assetid: 705b52e3-f695-4c58-9ae2-5a806f1e2140
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_GET_DEVICE_LOCATION, *PSRIOV_GET_DEVICE_LOCATION callback function pointer [Buses], PCI.sriov_get_device_location, SRIOV_GET_DEVICE_LOCATION, SriovGetDeviceLocation, SriovGetDeviceLocation callback function [Buses], pcivirt/SriovGetDeviceLocation"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Pcivirt.h
api_name:
-	*PSRIOV_GET_DEVICE_LOCATION
product: Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---


# SRIOV_GET_DEVICE_LOCATION callback function
Retrieves information about the current location of the PCI device on the bus, such as PCI Segment, Bus, Device and Function number.

## Syntax

```
SRIOV_GET_DEVICE_LOCATION SriovGetDeviceLocation;

void SriovGetDeviceLocation(
  PVOID Context,
  USHORT VfIndex,
  PUINT16 SegmentNumber,
  PUINT8 BusNumber,
  PUINT8 FunctionNumber
)
{...}
```

## Parameters

`Context`

A pointer to a driver-defined context.

`VfIndex`

A zero-based index of the VF to which this read operation applies.

`SegmentNumber`

A pointer to a variable that is filled in with the current Segment Number, which describes the group of PCI Buses to which this device is attached.

`BusNumber`

A pointer to a variable that is filled in with the current Bus Number, which describes which PCI Bus to which this device is attached.

`FunctionNumber`

A pointer to a variable that is filled in with the FunctionNumber, which further describes where on this bus the device can be found.


## Return Value

This callback function does not return a value.

## Remarks

This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to retrieve the device location. 

The PF driver registers its implementation by setting the <b>WriteVfConfigBlock</b> member of the <a href="https://msdn.microsoft.com/c71add7d-9920-4b2f-a46a-4a09a94f3900">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | pcivirt.h |
| **IRQL** | PASSIVE_LEVEL |