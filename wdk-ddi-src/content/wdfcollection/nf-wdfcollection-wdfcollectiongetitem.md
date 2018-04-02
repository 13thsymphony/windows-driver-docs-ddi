---
UID: NF:wdfcollection.WdfCollectionGetItem
title: WdfCollectionGetItem function
author: windows-driver-content
description: The WdfCollectionGetItem method returns a handle to the object that is contained in a specified object collection and associated with a specified index value.
old-location: wdf\wdfcollectiongetitem.htm
old-project: wdf
ms.assetid: 3bb6232c-b87e-4358-ba0c-8854d641bfd8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFCollectionObjectRef_8476d0ef-d5e3-4dbc-95de-bbabd04c22bc.xml, WdfCollectionGetItem, WdfCollectionGetItem method, kmdf.wdfcollectiongetitem, wdf.wdfcollectiongetitem, wdfcollection/WdfCollectionGetItem
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
-	WdfCollectionGetItem
product:
- Windows
targetos: Windows
req.typenames: WDF_CHILD_RETRIEVE_INFO, *PWDF_CHILD_RETRIEVE_INFO
req.product: Windows 10 or later.
---


# WdfCollectionGetItem function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCollectionGetItem</b> method returns a handle to the object that is contained in a specified object collection and associated with a specified index value.

## Syntax

```
WDFOBJECT WdfCollectionGetItem(
  WDFCOLLECTION Collection,
  ULONG         Index
);
```

## Parameters

`Collection`

A handle to a collection object.

`Index`

A zero-based index value that identifies an object in the collection.


## Return Value

<b>WdfCollectionGetItem</b> returns a framework object handle, or <b>NULL</b> if the <i>Index</i> value is invalid.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

Index values represent the order in which objects are added to a collection. An index value of zero represents the first object in the collection, an index value of one represents the second object, and so on, like a linked list. When the driver removes item <i>i</i> from a collection, item <i>i</i>+1 becomes item <i>i</i>. 

For more information about object collections, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.


#### Examples

For a code example that uses <b>WdfCollectionGetItem</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545759">WdfCollectionGetCount</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre></pre>
</td>
</tr>
</table></span></div>

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545763">WdfCollectionGetFirstItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545775">WdfCollectionGetLastItem</a>