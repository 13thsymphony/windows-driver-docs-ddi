---
UID: NF:wdfchildlist.WdfChildListBeginIteration
title: WdfChildListBeginIteration function
author: windows-driver-content
description: The WdfChildListBeginIteration method prepares the framework for retrieving items from a specified child list.
old-location: wdf\wdfchildlistbeginiteration.htm
old-project: wdf
ms.assetid: b81dbad8-0e03-4183-a7b3-32c75a656575
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_98150ed0-3144-4fda-96ca-41573d3013bf.xml, WdfChildListBeginIteration, WdfChildListBeginIteration method, kmdf.wdfchildlistbeginiteration, wdf.wdfchildlistbeginiteration, wdfchildlist/WdfChildListBeginIteration
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfchildlist.h
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
-	WdfChildListBeginIteration
product:
- Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---


# WdfChildListBeginIteration function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListBeginIteration</b> method prepares the framework for retrieving items from a specified child list.

## Syntax

```
void WdfChildListBeginIteration(
  WDFCHILDLIST             ChildList,
  PWDF_CHILD_LIST_ITERATOR Iterator
);
```

## Parameters

`ChildList`

A handle to a framework child list object.

`Iterator`

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551230">WDF_CHILD_LIST_ITERATOR</a> structure that indicates the type of child devices to be retrieved.


## Return Value

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

After calling <b>WdfChildListBeginIteration</b>, the driver can repeatedly call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a> to obtain information about each child device in the child list. 

After the driver has finished calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a>, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545618">WdfChildListEndIteration</a>.

If the driver makes changes to the child list after calling <b>WdfChildListBeginIteration</b>, the framework stores all of the changes and notifies the Plug and Play (PnP) manager of the changes when the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545618">WdfChildListEndIteration</a>.

The driver can nest calls to <b>WdfChildListBeginIteration</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff545618">WdfChildListEndIteration</a>. If the driver nests calls to these methods, the framework stores all of the changes until the last call to <b>WdfChildListEndIteration</b>.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WdfChildListBeginIteration</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfchildlist.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551225">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551230">WDF_CHILD_LIST_ITERATOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551232">WDF_CHILD_LIST_ITERATOR_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545608">WdfChildListBeginScan</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545618">WdfChildListEndIteration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545641">WdfChildListRequestChildEject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a>