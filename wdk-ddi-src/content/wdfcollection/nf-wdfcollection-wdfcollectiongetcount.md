---
UID : NF:wdfcollection.WdfCollectionGetCount
title : WdfCollectionGetCount function
author : windows-driver-content
description : The WdfCollectionGetCount method returns the number of objects that are currently in an object collection.
old-location : wdf\wdfcollectiongetcount.htm
old-project : wdf
ms.assetid : 95b6e441-f564-4642-8474-8e10e83177b9
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdfcollectiongetcount, PFN_WDFCOLLECTIONGETCOUNT, wdfcollection/WdfCollectionGetCount, DFCollectionObjectRef_835a8d24-fd48-4de9-83bc-62a8b5a3a93b.xml, kmdf.wdfcollectiongetcount, WdfCollectionGetCount, WdfCollectionGetCount method
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfcollection.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : <= DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_CHILD_RETRIEVE_INFO, *PWDF_CHILD_RETRIEVE_INFO
req.product : Windows 10 or later.
---


# WdfCollectionGetCount function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCollectionGetCount</b> method returns the number of objects that are currently in an object collection.

## Syntax

````
ULONG WdfCollectionGetCount(
  _In_ WDFCOLLECTION Collection
);
````

## Parameters

`Collection`

A handle to a collection object.


## Return Value

<b>WdfCollectionGetCount</b> returns the number of objects that are in the collection.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about object collections, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfcollection.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectiongetitem.md">WdfCollectionGetItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCollectionGetCount method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>