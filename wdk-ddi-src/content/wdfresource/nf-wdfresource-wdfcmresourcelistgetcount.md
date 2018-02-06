---
UID: NF:wdfresource.WdfCmResourceListGetCount
title: WdfCmResourceListGetCount function
author: windows-driver-content
description: The WdfCmResourceListGetCount method returns the number of resource descriptors that are contained in a specified resource list.
old-location: wdf\wdfcmresourcelistgetcount.htm
old-project: wdf
ms.assetid: f1a38276-4964-422d-9b3c-8450b1028f27
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfcmresourcelistgetcount, kmdf.wdfcmresourcelistgetcount, WdfCmResourceListGetCount, WdfCmResourceListGetCount method, PFN_WDFCMRESOURCELISTGETCOUNT, DFResourceObjectRef_8161cc12-7f39-44f4-a4a1-28329911ac96.xml, wdfresource/WdfCmResourceListGetCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
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
-	WdfCmResourceListGetCount
product: Windows
targetos: Windows
req.typenames: "*PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS"
req.product: Windows 10 or later.
---


# WdfCmResourceListGetCount function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCmResourceListGetCount</b> method returns the number of resource descriptors that are contained in a specified resource list.

## Syntax

````
ULONG WdfCmResourceListGetCount(
  _In_ WDFCMRESLIST List
);
````

## Parameters

`List`

A handle to a framework resource-list object that represents a list of hardware resources for a device.


## Return Value

<b>WdfCmResourceListGetCount</b> returns the number of resource descriptors that are contained in the resource list that the <i>List</i> parameter specifies.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about resource lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfresource.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |