---
UID: NF:wdfdevice.WdfDeviceAddRemovalRelationsPhysicalDevice
title: WdfDeviceAddRemovalRelationsPhysicalDevice function
author: windows-driver-content
description: The WdfDeviceAddRemovalRelationsPhysicalDevice method indicates that a specified device must be removed when another specified device is removed.
old-location: wdf\wdfdeviceaddremovalrelationsphysicaldevice.htm
old-project: wdf
ms.assetid: 4638905f-cefb-4bf0-aa00-64f2f096dc22
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_5e16c670-eb46-4c83-88e0-32eb41aeeac3.xml, WdfDeviceAddRemovalRelationsPhysicalDevice, WdfDeviceAddRemovalRelationsPhysicalDevice method, kmdf.wdfdeviceaddremovalrelationsphysicaldevice, wdf.wdfdeviceaddremovalrelationsphysicaldevice, wdfdevice/WdfDeviceAddRemovalRelationsPhysicalDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceAddRemovalRelationsPhysicalDevice
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceAddRemovalRelationsPhysicalDevice function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceAddRemovalRelationsPhysicalDevice</b> method indicates that a specified device must be removed when another specified device is removed.

## Syntax

```
NTSTATUS WdfDeviceAddRemovalRelationsPhysicalDevice(
  WDFDEVICE      Device,
  PDEVICE_OBJECT PhysicalDevice
);
```

## Parameters

`Device`

A handle to a framework device object.

`PhysicalDevice`

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents a physical device object (PDO).


## Return Value

If the operation succeeds, <b>WdfDeviceAddRemovalRelationsPhysicalDevice</b> returns STATUS_SUCCESS. Additional return values include:

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
<i>PhysicalDevice</i> is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A memory allocation failed.

</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <i>PhysicalDevice</i> parameter points to a PDO of a device whose drivers must be removed when the drivers for <i>Device</i> are removed. Typically, both devices are controlled by the calling driver. Do not report the child devices of the device object specified in <i>Device</i> because when the Plug and Play manager removes a parent device, it also removes the device's children.

Your driver can call <b>WdfDeviceAddRemovalRelationsPhysicalDevice</b> multiple times to add multiple devices to the list of devices that must be removed when <i>Device</i> is removed. The order in which the specified devices are removed is not defined.


#### Examples

The following code example adds the device that <b>pPdo</b> identifies to the list of devices that must be removed when the device that <b>device</b> specifies is removed.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>status = WdfDeviceAddRemovalRelationsPhysicalDevice(
                                                    device,
                                                    pPdo
                                                    );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545914">WdfDeviceClearRemovalRelationsDevices</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546834">WdfDeviceRemoveRemovalRelationsPhysicalDevice</a>