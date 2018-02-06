---
UID: NF:wdfresource.WdfIoResourceRequirementsListGetCount
title: WdfIoResourceRequirementsListGetCount function
author: windows-driver-content
description: The WdfIoResourceRequirementsListGetCount method returns the number of logical configurations that are contained in a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistgetcount.htm
old-project: wdf
ms.assetid: 00a79e57-5915-49a3-b11f-223cc93c2e99
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfresource/WdfIoResourceRequirementsListGetCount, WdfIoResourceRequirementsListGetCount method, DFResourceObjectRef_927d5729-0c1e-4363-9f2d-b5fefba8e2f6.xml, wdf.wdfioresourcerequirementslistgetcount, WdfIoResourceRequirementsListGetCount, PFN_WDFIORESOURCEREQUIREMENTSLISTGETCOUNT, kmdf.wdfioresourcerequirementslistgetcount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfIoResourceRequirementsListGetCount
product: Windows
targetos: Windows
req.typenames: "*PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS"
req.product: Windows 10 or later.
---


# WdfIoResourceRequirementsListGetCount function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceRequirementsListGetCount</b> method returns the number of <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configurations</a> that are contained in a resource requirements list.

## Syntax

````
ULONG WdfIoResourceRequirementsListGetCount(
  _In_ WDFIORESREQLIST RequirementsList
);
````

## Parameters

`RequirementsList`

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


## Return Value

<b>WdfIoResourceRequirementsListGetCount</b> returns the number of logical configurations that are contained in the resource requirements list.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfresource.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |