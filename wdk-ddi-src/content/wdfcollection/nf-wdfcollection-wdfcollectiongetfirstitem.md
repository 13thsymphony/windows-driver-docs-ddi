---
UID: NF:wdfcollection.WdfCollectionGetFirstItem
title: WdfCollectionGetFirstItem function
author: windows-driver-content
description: The WdfCollectionGetFirstItem method returns a handle to the first object that is in an object collection.
old-location: wdf\wdfcollectiongetfirstitem.htm
old-project: wdf
ms.assetid: 4884de4d-6e5f-4c9f-bd49-2fc58481e9c6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFCollectionObjectRef_1a816492-f120-48f9-9c10-88f71947008c.xml, WdfCollectionGetFirstItem, WdfCollectionGetFirstItem method, kmdf.wdfcollectiongetfirstitem, wdf.wdfcollectiongetfirstitem, wdfcollection/WdfCollectionGetFirstItem
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
-	WdfCollectionGetFirstItem
product:
- Windows
targetos: Windows
req.typenames: WDF_CHILD_RETRIEVE_INFO, *PWDF_CHILD_RETRIEVE_INFO
req.product: Windows 10 or later.
---


# WdfCollectionGetFirstItem function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCollectionGetFirstItem</b> method returns a handle to the first object that is in an object collection.

## Syntax

```
WDFOBJECT WdfCollectionGetFirstItem(
  WDFCOLLECTION Collection
);
```

## Parameters

`Collection`

A handle to a collection object.


## Return Value

<b>WdfCollectionGetFirstItem</b> returns a handle to the object that is currently at the front of the specified collection's list of objects, or <b>NULL</b> if the list is empty.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about object collections, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.


#### Examples

The following code example removes each item from a collection and deletes each item's object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>while ((subRequest = WdfCollectionGetFirstItem(hCollection)) != NULL) {
    WdfCollectionRemoveItem(
                            hCollection,
                            0
                            );
    WdfObjectDelete(subRequest);
}</pre>
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545770">WdfCollectionGetItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545775">WdfCollectionGetLastItem</a>