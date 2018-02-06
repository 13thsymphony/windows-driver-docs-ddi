---
UID: NF:wdffileobject.WdfFileObjectGetFlags
title: WdfFileObjectGetFlags function
author: windows-driver-content
description: The WdfFileObjectGetFlags method returns the flags that a specified framework file object contains.
old-location: wdf\wdffileobjectgetflags.htm
old-project: wdf
ms.assetid: f2f30acb-cab7-444a-8b86-6001a8a325b9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFFILEOBJECTGETFLAGS, wdf.wdffileobjectgetflags, kmdf.wdffileobjectgetflags, WdfFileObjectGetFlags, WdfFileObjectGetFlags method, DFFileObjectRef_5f2f8f12-9a16-4fb5-88ae-ee726a278cc5.xml, wdffileobject/WdfFileObjectGetFlags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffileobject.h
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
-	WdfFileObjectGetFlags
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---


# WdfFileObjectGetFlags function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFileObjectGetFlags</b> method returns the flags that a specified framework file object contains.

## Syntax

````
ULONG WdfFileObjectGetFlags(
  _In_ WDFFILEOBJECT FileObject
);
````

## Parameters

`FileObject`

A handle to a framework file object.


## Return Value

<b>WdfFileObjectGetFlags</b> returns a bitwise OR of file object flags. The flag names have a format of FO_<i>XXX</i> and are defined in <i>Wdm.h</i>. 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about framework file objects, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdffileobject.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |