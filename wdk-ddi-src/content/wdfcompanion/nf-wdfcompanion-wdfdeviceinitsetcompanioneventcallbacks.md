---
UID: NF:wdfcompanion.WdfDeviceInitSetCompanionEventCallbacks
title: WdfDeviceInitSetCompanionEventCallbacks function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfdeviceinitsetcompanioneventcallbacks.htm
old-project: wdf
ms.assetid: 7320238d-0c7f-423c-8de7-2b22d02d77bd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDeviceInitSetCompanionEventCallbacks, WdfDeviceInitSetCompanionEventCallbacks method, wdf.wdfdeviceinitsetcompanioneventcallbacks, wdfcompanion/WdfDeviceInitSetCompanionEventCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcompanion.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.23
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfcompanion.h
api_name:
-	WdfDeviceInitSetCompanionEventCallbacks
product:
- Windows
targetos: Windows
req.typenames: WDF_TASK_QUEUE_DISPATCH_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceInitSetCompanionEventCallbacks function
For internal use only.

## Syntax

```
void WdfDeviceInitSetCompanionEventCallbacks(
  PWDFDEVICE_INIT                DeviceInit,
  PWDF_COMPANION_EVENT_CALLBACKS CompanionEventCallbacks
);
```

## Parameters

`DeviceInit`



`CompanionEventCallbacks`




## Return Value

This method does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum UMDF version** | 2.23 |
| **Header** | wdfcompanion.h |
| **IRQL** | PASSIVE_LEVEL |