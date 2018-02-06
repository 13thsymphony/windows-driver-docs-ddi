---
UID: NF:wdfcollection.WdfCollectionGetItem
title: WdfCollectionGetItem function
author: windows-driver-content
description: The WdfCollectionGetItem method returns a handle to the object that is contained in a specified object collection and associated with a specified index value.
old-location: wdf\wdfcollectiongetitem.htm
old-project: wdf
ms.assetid: 3bb6232c-b87e-4358-ba0c-8854d641bfd8
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfCollectionGetItem, DFCollectionObjectRef_8476d0ef-d5e3-4dbc-95de-bbabd04c22bc.xml, PFN_WDFCOLLECTIONGETITEM, kmdf.wdfcollectiongetitem, WdfCollectionGetItem method, wdf.wdfcollectiongetitem, wdfcollection/WdfCollectionGetItem
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
-	WdfCollectionGetItem
product: Windows
targetos: Windows
req.typenames: "*PWDF_CHILD_RETRIEVE_INFO, WDF_CHILD_RETRIEVE_INFO"
req.product: Windows 10 or later.
---


# WdfCollectionGetItem function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCollectionGetItem</b> method returns a handle to the object that is contained in a specified object collection and associated with a specified index value.

## Syntax

````
WDFOBJECT WdfCollectionGetItem(
  _In_ WDFCOLLECTION Collection,
  _In_ ULONG         Index
);
````

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

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectiongetlastitem.md">WdfCollectionGetLastItem</a>

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectiongetfirstitem.md">WdfCollectionGetFirstItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCollectionGetItem method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>