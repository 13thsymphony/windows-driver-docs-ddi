---
UID: NF:wdfdevice.WdfDeviceAssignProperty
title: WdfDeviceAssignProperty function
author: windows-driver-content
description: The WdfDeviceAssignProperty method modifies the current setting of a device property.
old-location: wdf\wdfdeviceassignproperty.htm
old-project: wdf
ms.assetid: 5110C452-53E6-401A-9D14-EBD95D3F8BE2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDeviceAssignProperty, WdfDeviceAssignProperty method, wdf.wdfdeviceassignproperty, wdfdevice/WdfDeviceAssignProperty
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: APC_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceAssignProperty
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceAssignProperty function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceAssignProperty</b> method modifies the current setting of a device property.

## Syntax

````
NTSTATUS WdfDeviceAssignProperty(
  _In_     WDFDEVICE                 Device,
  _In_     PWDF_DEVICE_PROPERTY_DATA DeviceProperty,
  _In_     DEVPROPTYPE               Type,
  _In_     ULONG                     Size,
  _In_opt_ PVOID                     Data
);
````

## Parameters

`Device`

A handle to a framework device object.

`DeviceProperty`

A pointer to a <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_property_data.md">WDF_DEVICE_PROPERTY_DATA</a> structure that identifies the device property to modify.

`Type`

A <b>DEVPROPTYPE</b>-typed variable that specifies the type of the data stored in <i>Data</i>.

`Size`

The size, in bytes, of the buffer that is pointed to by <i>Data</i>.

`Data`

A pointer to a caller-allocated buffer that contains the device property data. Set this parameter to <b>NULL</b> to delete the specified property.


## Return Value

If the operation succeeds, <b>WdfDeviceAssignProperty</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters is incorrect.

</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

You can use <b>WdfDeviceAssignProperty</b> to modify the setting of any property that is exposed through the unified property model.

For information about related methods, see <a href="https://msdn.microsoft.com/C81988F9-E0DA-439F-B770-DAD86E33D5F3">Accessing the Unified Device Property Model</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | APC_LEVEL |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigninterfaceproperty.md">WdfDeviceAssignInterfaceProperty</a>