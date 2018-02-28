---
UID: NF:wdfcollection.WdfCollectionRemoveItem
title: WdfCollectionRemoveItem function
author: windows-driver-content
description: The WdfCollectionRemoveItem method removes a specified object from an object collection, based on a specified index value.
old-location: wdf\wdfcollectionremoveitem.htm
old-project: wdf
ms.assetid: 03fde4a7-a4d1-4045-ac0c-6a37f2367b9d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFCollectionObjectRef_a037497e-b219-41c1-8d65-29cf8be17989.xml, WdfCollectionRemoveItem, WdfCollectionRemoveItem method, kmdf.wdfcollectionremoveitem, wdf.wdfcollectionremoveitem, wdfcollection/WdfCollectionRemoveItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcollection.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfCollectionRemoveItem
product: Windows
targetos: Windows
req.typenames: WDF_CHILD_RETRIEVE_INFO, *PWDF_CHILD_RETRIEVE_INFO
req.product: Windows 10 or later.
---


# WdfCollectionRemoveItem function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCollectionRemoveItem</b> method removes a specified object from an object collection, based on a specified index value.

## Syntax

````
VOID WdfCollectionRemoveItem(
  _In_ WDFCOLLECTION Collection,
  _In_ ULONG         Index
);
````

## Parameters

`Collection`

A handle to a collection object.

`Index`

A zero-based index that identifies the object to remove.


## Return Value

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

Index values represent the order in which objects are added to a collection. An index value of zero represents the first object that was added to the collection, an index value of one represents the second object, and so on. 

When <b>WdfCollectionRemoveItem</b> removes an object from a collection, it decrements the object's reference count. 

For more information about object collections, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>



#### Examples

For a code example that uses <b>WdfCollectionRemoveItem</b>, see <a href="..\wdfcollection\nf-wdfcollection-wdfcollectiongetfirstitem.md">WdfCollectionGetFirstItem</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfcollection.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectionremove.md">WdfCollectionRemove</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCollectionRemoveItem method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>