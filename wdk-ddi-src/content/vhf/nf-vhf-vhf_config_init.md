---
UID: NF:vhf.VHF_CONFIG_INIT
title: VHF_CONFIG_INIT function
author: windows-driver-content
description: Use the VHF_CONFIG_INIT function to initialize the required members of the VHF_CONFIG structure allocated by the HID source driver.
old-location: hid\vhf_config_init.htm
old-project: hid
ms.assetid: 4A87D9E2-F1FC-4CA8-834C-E545D8F0277B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: VHF_CONFIG_INIT, VHF_CONFIG_INIT function [Human Input Devices], hid.vhf_config_init, vhf/VHF_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vhf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: VhfKm.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	vhfKm.lib
-	vhfKm.dll
api_name:
-	VHF_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
req.product: Windows 10 or later.
---


# VHF_CONFIG_INIT function
Use the <b>VHF_CONFIG_INIT</b> function to initialize the required members of the <a href="..\vhf\ns-vhf-_vhf_config.md">VHF_CONFIG</a> structure allocated by the HID source driver.

## Syntax

````
FORCEINLINE void VHF_CONFIG_INIT(
  _Out_ PVHF_CONFIG                                     Config,
  _In_  PDEVICE_OBJECT                                  DeviceObject,
  _In_  USHORT                                          ReportDescriptorLength,
        _In_reads_bytes_(ReportDescriptorLength) PUCHAR ReportDescriptor
);
````

## Parameters

`Config`

A pointer to the <a href="..\vhf\ns-vhf-_vhf_config.md">VHF_CONFIG</a> structure to initialize.

`DeviceObject`

A pointer to the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure for the HID source driver. Get that pointer by calling  <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmgetdeviceobject.md">WdfDeviceWdmGetDeviceObject</a> and passing the WDFDEVICE handle that the driver received in the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> call.

`ReportDescriptorLength`

The length of the HID Report Descriptor contained in a buffer pointer by <i>ReportDescriptor</i>.

`ReportDescriptor`

A pointer to a HID source driver-allocated buffer that contains the  HID Report Descriptor.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 None supported |
| **Target Platform** | Desktop |
| **Header** | vhf.h |
| **Library** | VhfKm.lib |

## See Also

<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>