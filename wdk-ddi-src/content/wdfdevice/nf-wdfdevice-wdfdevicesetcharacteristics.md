---
UID: NF:wdfdevice.WdfDeviceSetCharacteristics
title: WdfDeviceSetCharacteristics function
author: windows-driver-content
description: The WdfDeviceSetCharacteristics method sets device characteristics for a specified device.
old-location: wdf\wdfdevicesetcharacteristics.htm
old-project: wdf
ms.assetid: 07b5d7ed-fc4c-45e5-8748-2630c91d912a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_a5d23cdb-a42e-48ef-9158-174354e13ca6.xml, WdfDeviceSetCharacteristics, WdfDeviceSetCharacteristics method, kmdf.wdfdevicesetcharacteristics, wdf.wdfdevicesetcharacteristics, wdfdevice/WdfDeviceSetCharacteristics
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceSetCharacteristics
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceSetCharacteristics function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceSetCharacteristics</b> method sets device characteristics for a specified device.

## Syntax

```
void WdfDeviceSetCharacteristics(
  WDFDEVICE Device,
  ULONG     DeviceCharacteristics
);
```

## Parameters

`Device`

A handle to a framework device object.

`DeviceCharacteristics`

A value that consists of ORed system-defined constants that represent device characteristics. For more information, see the <b>Characteristics</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

You should set device characteristics by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546074">WdfDeviceInitSetCharacteristics</a> method in your <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. If your driver cannot determine a device's characteristics until after the <i>EvtDriverDeviceAdd</i> callback function returns, the driver typically should call <b>WdfDeviceSetCharacteristics</b> in its <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function.

Each call to <b>WdfDeviceSetCharacteristics</b> overwrites the settings of any previous call.


#### Examples

The following code example sets the FILE_REMOVABLE_MEDIA characteristic for a specified device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDeviceSetCharacteristics(
                            Device,
                            FILE_REMOVABLE_MEDIA
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
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545960">WdfDeviceGetCharacteristics</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546074">WdfDeviceInitSetCharacteristics</a>