---
UID: NF.wdfdevice.WDF_DEVICE_PROPERTY_DATA_INIT
title: WDF_DEVICE_PROPERTY_DATA_INIT function
author: windows-driver-content
description: The WDF_DEVICE_PROPERTY_DATA_INIT function initializes a driver's WDF_DEVICE_PROPERTY_DATA structure.
old-location: wdf\wdf_device_property_data_init.htm
old-project: wdf
ms.assetid: D3A7646A-49A8-499E-A63A-BCD222DF7804
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WDF_DEVICE_PROPERTY_DATA_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: WDF_DEVICE_PROPERTY_DATA_INIT
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
req.product: Windows 10 or later.
---

# WDF_DEVICE_PROPERTY_DATA_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> function initializes a driver's <a href="wdf.wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure.



## -syntax

````
void WDF_DEVICE_PROPERTY_DATA_INIT(
  _In_       PWDF_DEVICE_INTERFACE_PROPERTY_DATA PropertyData,
  _In_ const DEVPROPKEY                          *PropertyKey
);
````


## -parameters

### -param PropertyData [in]

A pointer to <a href="wdf.wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure.


### -param PropertyKey [in]

A pointer to a <b>DEVPROPKEY</b> structure that specifies the device property key.


## -returns
This function does not return a value.


## -remarks
Before calling the following methods, a driver must call <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> to initialize a <a href="wdf.wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure.

The <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> function zeros the specified <a href="wdf.wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>PropertyKey</b> member to the specified value.


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
Minimum KMDF version

</th>
<td width="70%">
1.13

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
<a href="wdf.wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a>
</dt>
<dt>
<a href="wdf.wdfdeviceallocandquerypropertyex">WdfDeviceAllocAndQueryPropertyEx</a>
</dt>
<dt>
<a href="wdf.wdfdeviceassignproperty">WdfDeviceAssignProperty</a>
</dt>
<dt>
<a href="wdf.wdfdevicequerypropertyex">WdfDeviceQueryPropertyEx</a>
</dt>
<dt>
<a href="wdf.wdffdoinitallocandquerypropertyex">WdfFdoInitAllocAndQueryPropertyEx</a>
</dt>
<dt>
<a href="wdf.wdffdoinitquerypropertyex">WdfFdoInitQueryPropertyEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_PROPERTY_DATA_INIT function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

