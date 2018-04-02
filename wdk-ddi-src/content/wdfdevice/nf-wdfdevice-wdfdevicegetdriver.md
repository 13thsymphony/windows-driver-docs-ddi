---
UID: NF:wdfdevice.WdfDeviceGetDriver
title: WdfDeviceGetDriver function
author: windows-driver-content
description: The WdfDeviceGetDriver method returns a handle to the framework driver object that is associated with a specified framework device object.
old-location: wdf\wdfdevicegetdriver.htm
old-project: wdf
ms.assetid: 774cce7b-37bf-495b-8087-915b164745ba
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_821bd67e-0a04-4664-91e1-4fa608a8b93e.xml, WdfDeviceGetDriver, WdfDeviceGetDriver method, kmdf.wdfdevicegetdriver, wdf.wdfdevicegetdriver, wdfdevice/WdfDeviceGetDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
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
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceGetDriver
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceGetDriver function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceGetDriver</b> method returns a handle to the framework driver object that is associated with a specified framework device object.

## Syntax

```
WDFDRIVER WdfDeviceGetDriver(
  WDFDEVICE Device
);
```

## Parameters

`Device`

A handle to a framework device object.


## Return Value

<b>WdfDeviceGetDriver</b> returns a handle to a framework driver object. 

A bug check occurs if the driver supplies an invalid object handle.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547187">WdfDriverGetRegistryPath</a>