---
UID: NF.ucxroothub.UcxRootHubPortChanged
title: UcxRootHubPortChanged function
author: windows-driver-content
description: Notifies UCX about a new port change event on the host controller.
old-location: buses\_ucxroothubportchanged.htm
old-project: UsbRef
ms.assetid: 7984308D-4C8E-4481-8770-2430552B00E8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: UcxRootHubPortChanged
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: UcxRootHubPortChanged
req.alt-loc: ucxroothub.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# UcxRootHubPortChanged function



## -description
Notifies UCX about a new port change event on the host controller.




## -syntax

````
void UcxRootHubPortChanged(
  [in] UCXROOTHUB UcxRootHub
);
````


## -parameters

### -param UcxRootHub [in]

A handle to the root hub object. The client driver retrieved the handle in a previous call to <a href="buses._ucxroothubcreate">UcxRootHubCreate</a>.


## -returns
This method does not return a value.


## -remarks
This method causes interrupt transfers to be sent to the host controller. UCX invokes the client driver's implementation of the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_interrupt_tx.md">EVT_UCX_ROOTHUB_INTERRUPT_TX</a> event callback.


## -requirements
<table>
<tr>
<th width="30%">
Minimum support

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucxroothub.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses._ucxroothubcreate">UcxRootHubCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UcxRootHubPortChanged method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

