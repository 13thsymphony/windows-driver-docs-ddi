---
UID: NF:wdfresource.WdfIoResourceListGetDescriptor
title: WdfIoResourceListGetDescriptor function
author: windows-driver-content
description: The WdfIoResourceListGetDescriptor method returns a pointer to a resource descriptor that is contained in a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistgetdescriptor.htm
old-project: wdf
ms.assetid: 1722e6f6-7509-4ae1-b394-3c69f4596e6d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_6cb56ab5-abf5-4915-a48f-a3c91d657806.xml, WdfIoResourceListGetDescriptor, WdfIoResourceListGetDescriptor method, kmdf.wdfioresourcelistgetdescriptor, wdf.wdfioresourcelistgetdescriptor, wdfresource/WdfIoResourceListGetDescriptor
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfIoResourceListGetDescriptor
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---


# WdfIoResourceListGetDescriptor function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceListGetDescriptor</b> method returns a pointer to a resource descriptor that is contained in a resource requirements list's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>.

## Syntax

````
PIO_RESOURCE_DESCRIPTOR WdfIoResourceListGetDescriptor(
  _In_ WDFIORESLIST ResourceList,
  _In_ ULONG        Index
);
````

## Parameters

`ResourceList`

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.

`Index`

A zero-based value that is used as an index into the logical configuration that <i>ResourceList</i> specifies.


## Return Value

<b>WdfIoResourceListGetDescriptor</b> returns a pointer to the <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure that describes the hardware resource that the <i>Index</i> parameter identifies, if the index value is valid. Otherwise, the method returns <b>NULL</b>.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

Your driver cannot modify the contents of the <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure that <b>WdfIoResourceListGetDescriptor</b> retrieves. To modify a resource descriptor, the driver can call <a href="..\wdfresource\nf-wdfresource-wdfioresourcelistupdatedescriptor.md">WdfIoResourceListUpdateDescriptor</a>.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

For a code example that uses <b>WdfIoResourceListGetDescriptor</b>, see <a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistgetioreslist.md">WdfIoResourceRequirementsListGetIoResList</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfresource.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>



<a href="..\wdfresource\nf-wdfresource-wdfioresourcelistupdatedescriptor.md">WdfIoResourceListUpdateDescriptor</a>