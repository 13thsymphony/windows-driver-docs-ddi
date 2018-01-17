---
UID: NF:wdfchildlist.WdfChildListEndScan
title: WdfChildListEndScan function
author: windows-driver-content
description: The WdfChildListEndScan method processes modifications to a specified child list.
old-location: wdf\wdfchildlistendscan.htm
old-project: wdf
ms.assetid: 73891793-e59f-4c67-af93-07929d7c7326
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfChildListEndScan
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
req.alt-api: WdfChildListEndScan
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WdfChildListEndScan function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListEndScan</b> method processes modifications to a specified child list. 



## -syntax

````
VOID WdfChildListEndScan(
  _In_ WDFCHILDLIST ChildList
);
````


## -parameters

### -param ChildList [in]

The same handle to a framework child-list object that the driver previously specified to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>.


## -returns
None.

A system bug check occurs if the driver supplies an invalid object handle.



## -remarks
If the driver has made multiple calls to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>, the framework does not process modifications to the child list until the driver has made a corresponding number of calls to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a> and <b>WdfChildListEndScan</b>.

For more information about child lists, see <a href="https://msdn.microsoft.com/6e46b456-7d2d-4c6e-8692-7f310366387d">Dynamic Enumeration</a>.

For a code example that uses <b>WdfChildListEndScan</b>, see <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfChildListEndScan method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

