---
UID: NF:wdfdevice.WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT
title: WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT function
author: windows-driver-content
description: The WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT function initializes a driver's WDF_DEVICE_INTERFACE_PROPERTY_DATA structure.
old-location: wdf\wdf_device_interface_property_data_init.htm
old-project: wdf
ms.assetid: 8B3D6F59-BA76-4B14-9570-57263D204BFE
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.alt-api: WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT
req.alt-loc: wdfdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT function



## -description
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</b> function initializes a driver's <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_interface_property_data.md">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a> structure.



## -syntax

````
void WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT(
  _In_       PWDF_DEVICE_INTERFACE_PROPERTY_DATA PropertyData,
  _In_ const GUID                                *InterfaceClassGUID,
  _In_ const DEVPROPKEY                          *PropertyKey
);
````


## -parameters

### -param PropertyData [in]

A pointer to <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_interface_property_data.md">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a> structure.


### -param InterfaceClassGUID [in]

A pointer to a GUID that identifies the device interface class.


### -param PropertyKey [in]

A pointer to a <b>DEVPROPKEY</b> structure that specifies the device property key.


## -returns
This function does not return a value.


## -remarks
Before calling the following methods, a driver must call <b>WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</b> to initialize a <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_interface_property_data.md">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a> structure.

The <b>WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</b> function zeros the specified <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_interface_property_data.md">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>InterfaceClassGUID</b> and <b>PropertyKey</b> members to the specified values.

For a code example that uses <b>WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</b>, see <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigninterfaceproperty.md">WdfDeviceAssignInterfaceProperty</a>.


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
Minimum support

</th>
<td width="70%">
Windows 8.1

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
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_interface_property_data.md">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandqueryinterfaceproperty.md">WdfDeviceAllocAndQueryInterfaceProperty</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigninterfaceproperty.md">WdfDeviceAssignInterfaceProperty</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryinterfaceproperty.md">WdfDeviceQueryInterfaceProperty</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

