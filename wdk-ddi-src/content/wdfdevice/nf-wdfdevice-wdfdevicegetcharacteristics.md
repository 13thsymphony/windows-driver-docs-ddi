---
UID: NF:wdfdevice.WdfDeviceGetCharacteristics
title: WdfDeviceGetCharacteristics function
author: windows-driver-content
description: The WdfDeviceGetCharacteristics method returns device characteristics for a specified device.
old-location: wdf\wdfdevicegetcharacteristics.htm
old-project: wdf
ms.assetid: 985dcde1-5643-4c35-9096-44b076a1dd51
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_b6e7566f-59b1-46ee-ab3d-45fa7316336e.xml, WdfDeviceGetCharacteristics, WdfDeviceGetCharacteristics method, kmdf.wdfdevicegetcharacteristics, wdf.wdfdevicegetcharacteristics, wdfdevice/WdfDeviceGetCharacteristics
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
-	WdfDeviceGetCharacteristics
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceGetCharacteristics function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceGetCharacteristics</b> method returns device characteristics for a specified device.

## Syntax

```
ULONG WdfDeviceGetCharacteristics(
  WDFDEVICE Device
);
```

## Parameters

`Device`

A handle to a framework device object.


## Return Value

A bitwise OR of system-defined constants that represent device characteristics. For more information, see the <b>Characteristics</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure.

A bug check occurs if the driver supplies an invalid object handle.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546074">WdfDeviceInitSetCharacteristics</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546872">WdfDeviceSetCharacteristics</a>