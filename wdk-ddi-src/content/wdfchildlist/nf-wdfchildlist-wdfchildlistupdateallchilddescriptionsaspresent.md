---
UID : NF:wdfchildlist.WdfChildListUpdateAllChildDescriptionsAsPresent
title : WdfChildListUpdateAllChildDescriptionsAsPresent function
author : windows-driver-content
description : The WdfChildListUpdateAllChildDescriptionsAsPresent method informs the framework that all of the child devices in a specified child list are plugged in and available.
old-location : wdf\wdfchildlistupdateallchilddescriptionsaspresent.htm
old-project : wdf
ms.assetid : 598d2b4f-9b49-480a-9cf8-25661c24483f
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : kmdf.wdfchildlistupdateallchilddescriptionsaspresent, wdfchildlist/WdfChildListUpdateAllChildDescriptionsAsPresent, PFN_WDFCHILDLISTUPDATEALLCHILDDESCRIPTIONSASPRESENT, WdfChildListUpdateAllChildDescriptionsAsPresent, WdfChildListUpdateAllChildDescriptionsAsPresent method, wdf.wdfchildlistupdateallchilddescriptionsaspresent, DFDeviceObjectChildListRef_55956590-2843-4486-acfb-0e85c01702a0.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfchildlist.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_RETRIEVE_CHILD_FLAGS
req.product : Windows 10 or later.
---


# WdfChildListUpdateAllChildDescriptionsAsPresent function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListUpdateAllChildDescriptionsAsPresent</b> method informs the framework that all of the child devices in a specified child list are plugged in and available.

## Syntax

````
VOID WdfChildListUpdateAllChildDescriptionsAsPresent(
  _In_ WDFCHILDLIST ChildList
);
````

## Parameters

`ChildList`

A handle to a child list object.


## Return Value

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <b>WdfChildListUpdateAllChildDescriptionsAsPresent</b> method is available in version 1.0 and later versions of KMDF.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfchildlist.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |