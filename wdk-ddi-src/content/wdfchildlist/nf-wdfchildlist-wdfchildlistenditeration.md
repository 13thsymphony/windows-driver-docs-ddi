---
UID: NF:wdfchildlist.WdfChildListEndIteration
title: WdfChildListEndIteration function
author: windows-driver-content
description: The WdfChildListEndIteration method processes modifications to a specified child list.
old-location: wdf\wdfchildlistenditeration.htm
old-project: wdf
ms.assetid: f8dc1d77-d0c5-4112-939d-221955012de1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_24a52e50-851e-456f-b111-0b794e76acfb.xml, WdfChildListEndIteration, WdfChildListEndIteration method, kmdf.wdfchildlistenditeration, wdf.wdfchildlistenditeration, wdfchildlist/WdfChildListEndIteration
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
-	WdfChildListEndIteration
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---


# WdfChildListEndIteration function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListEndIteration</b> method processes modifications to a specified child list.

## Syntax

````
VOID WdfChildListEndIteration(
  _In_ WDFCHILDLIST             ChildList,
  _In_ PWDF_CHILD_LIST_ITERATOR Iterator
);
````

## Parameters

`ChildList`

The same handle to a framework child-list object that the driver previously specified to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>.

`Iterator`

A pointer to the same caller-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a> structure that the driver previously supplied to <b>WdfChildListEndIteration</b>.


## Return Value

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

If the driver has made multiple calls to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>, the framework does not process modifications to the child list until the driver has made a corresponding number of calls to <b>WdfChildListEndIteration</b> and <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistendscan.md">WdfChildListEndScan</a>.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WdfChildListEndIteration</b>, see <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>.

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

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistendscan.md">WdfChildListEndScan</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>



<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfChildListEndIteration method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>