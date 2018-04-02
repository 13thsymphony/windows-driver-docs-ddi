---
UID: NF:wdfdevice.WdfDeviceInitSetCharacteristics
title: WdfDeviceInitSetCharacteristics function
author: windows-driver-content
description: The WdfDeviceInitSetCharacteristics method sets device characteristics for a specified device.
old-location: wdf\wdfdeviceinitsetcharacteristics.htm
old-project: wdf
ms.assetid: 2937d9f1-f838-4ec4-972d-21ff43097590
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_7dd76de2-8621-45ed-a309-c958ac1c365d.xml, WdfDeviceInitSetCharacteristics, WdfDeviceInitSetCharacteristics method, kmdf.wdfdeviceinitsetcharacteristics, wdf.wdfdeviceinitsetcharacteristics, wdfdevice/WdfDeviceInitSetCharacteristics
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
req.ddi-compliance: ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
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
-	WdfDeviceInitSetCharacteristics
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceInitSetCharacteristics function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitSetCharacteristics</b> method sets device characteristics for a specified device.

## Syntax

```
void WdfDeviceInitSetCharacteristics(
  PWDFDEVICE_INIT DeviceInit,
  ULONG           DeviceCharacteristics,
  BOOLEAN         OrInValues
);
```

## Parameters

`DeviceInit`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.

`DeviceCharacteristics`

A value that consists of ORed system-defined constants that represent device characteristics. For more information, see the <b>Characteristics</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure.

`OrInValues`

A Boolean value. If this value is <b>TRUE</b>, the <i>DeviceCharacteristics</i> value is ORed with existing device characteristics. If the value is <b>FALSE</b>, the <i>DeviceCharacteristics</i> value replaces existing device characteristics.


## Return Value

None

## Remarks

To set device characteristics, call the <b>WdfDeviceInitSetCharacteristics</b> method in your <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. If your driver cannot determine a device's characteristics until after the <i>EvtDriverDeviceAdd</i> callback function returns, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546872">WdfDeviceSetCharacteristics</a>.

For more information about calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

The framework always sets the FILE_DEVICE_SECURE_OPEN characteristic, so your driver does not have to set this characteristic.

Each call to <b>WdfDeviceInitSetCharacteristics</b> overwrites the settings of any previous call.


#### Examples

The following code example indicates that a device is a floppy disk.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDeviceInitSetCharacteristics(
                                DeviceInit,
                                FILE_FLOPPY_DISKETTE,
                                FALSE
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
| **DDI compliance rules** | ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546872">WdfDeviceSetCharacteristics</a>