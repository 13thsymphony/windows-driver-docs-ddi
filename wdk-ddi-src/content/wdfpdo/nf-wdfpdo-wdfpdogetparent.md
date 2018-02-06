---
UID: NF:wdfpdo.WdfPdoGetParent
title: WdfPdoGetParent function
author: windows-driver-content
description: The WdfPdoGetParent method returns a handle to the framework device object that represents the parent device of a specified device.
old-location: wdf\wdfpdogetparent.htm
old-project: wdf
ms.assetid: 62a2a316-afb4-4133-b256-933ea04c0994
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfpdogetparent, PFN_WDFPDOGETPARENT, kmdf.wdfpdogetparent, WdfPdoGetParent, wdfpdo/WdfPdoGetParent, DFDeviceObjectFdoPdoRef_19cc338e-2040-4e60-8e6f-7be6dbb33c13.xml, WdfPdoGetParent method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfPdoGetParent
product: Windows
targetos: Windows
req.typenames: "*PWDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO"
req.product: Windows 10 or later.
---


# WdfPdoGetParent function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoGetParent</b> method returns a handle to the framework device object that represents the parent device of a specified device.

## Syntax

````
WDFDEVICE WdfPdoGetParent(
  _In_ WDFDEVICE Device
);
````

## Parameters

`Device`

A handle to a framework device object that represents the device's physical device object (PDO).


## Return Value

The method returns a handle to the framework device object that represents the specified device's parent, or <b>NULL</b> if the <i>Device</i> value does not represent a PDO. 

A system bug check occurs if the driver supplies an invalid object handle.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfpdo.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |