---
UID: NF:wdffileobject.WdfFileObjectGetDevice
title: WdfFileObjectGetDevice function
author: windows-driver-content
description: The WdfFileObjectGetDevice method returns the framework device object that is associated with a specified framework file object.
old-location: wdf\wdffileobjectgetdevice.htm
old-project: wdf
ms.assetid: 10bb8bbd-0347-4ceb-844e-87f049813684
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfFileObjectGetDevice method, PFN_WDFFILEOBJECTGETDEVICE, kmdf.wdffileobjectgetdevice, WdfFileObjectGetDevice, wdf.wdffileobjectgetdevice, DFFileObjectRef_4986a619-be10-4eca-84dd-9ae1dcac423f.xml, wdffileobject/WdfFileObjectGetDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffileobject.h
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfFileObjectGetDevice
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---


# WdfFileObjectGetDevice function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfFileObjectGetDevice</b> method returns the framework device object that is associated with a specified framework file object.

## Syntax

````
WDFDEVICE WdfFileObjectGetDevice(
  _In_ WDFFILEOBJECT FileObject
);
````

## Parameters

`FileObject`

A handle to a framework file object.


## Return Value

<b>WdfFileObjectGetDevice</b> returns a handle to the framework device object that is associated with the specified framework file object.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about framework file objects, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdffileobject.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |