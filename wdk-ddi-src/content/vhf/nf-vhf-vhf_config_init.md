---
UID: NF.vhf.VHF_CONFIG_INIT
title: VHF_CONFIG_INIT function
author: windows-driver-content
description: Use the VHF_CONFIG_INIT function to initialize the required members of the VHF_CONFIG structure allocated by the HID source driver.
old-location: hid\vhf_config_init.htm
old-project: hid
ms.assetid: 4A87D9E2-F1FC-4CA8-834C-E545D8F0277B
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: VHF_CONFIG_INIT
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
req.alt-api: VHF_CONFIG_INIT
req.alt-loc: vhfKm.lib,vhfKm.dll
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
req.product: Windows 10 or later.
---

# VHF_CONFIG_INIT function



## -description
Use the <b>VHF_CONFIG_INIT</b> function to initialize the required members of the <a href="hid.vhf_config">VHF_CONFIG</a> structure allocated by the HID source driver.



## -syntax

````
FORCEINLINE void VHF_CONFIG_INIT(
  _Out_ PVHF_CONFIG                                     Config,
  _In_  PDEVICE_OBJECT                                  DeviceObject,
  _In_  USHORT                                          ReportDescriptorLength,
        _In_reads_bytes_(ReportDescriptorLength) PUCHAR ReportDescriptor
);
````


## -parameters

### -param Config [out]

A pointer to the <a href="hid.vhf_config">VHF_CONFIG</a> structure to initialize.


### -param DeviceObject [in]

A pointer to the <a href="kernel.device_object">DEVICE_OBJECT</a> structure for the HID source driver. Get that pointer by calling  <a href="wdf.wdfdevicewdmgetdeviceobject">WdfDeviceWdmGetDeviceObject</a> and passing the WDFDEVICE handle that the driver received in the <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a> call. 


### -param ReportDescriptorLength [in]

The length of the HID Report Descriptor contained in a buffer pointer by <i>ReportDescriptor</i>.


### -param ReportDescriptor 

A pointer to a HID source driver-allocated buffer that contains the  HID Report Descriptor.


## -returns
This function does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
None supported

</td>
</tr>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Vhf.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>VhfKm.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20VHF_CONFIG_INIT function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

