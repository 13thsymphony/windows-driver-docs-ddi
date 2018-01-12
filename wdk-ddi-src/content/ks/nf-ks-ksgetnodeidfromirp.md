---
UID: NF:ks.KsGetNodeIdFromIrp
title: KsGetNodeIdFromIrp function
author: windows-driver-content
description: The KsGetNodeIdFromIrp function returns the node ID of the node to which Irp was submitted.
old-location: stream\ksgetnodeidfromirp.htm
old-project: stream
ms.assetid: 3bb115eb-074d-4983-97e4-fa38aaa8a81b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsGetNodeIdFromIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsGetNodeIdFromIrp
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: Any level
req.typenames: 
---

# KsGetNodeIdFromIrp function



## -description
The<b> KsGetNodeIdFromIrp </b>function returns the node ID of the node to which <i>Irp</i> was submitted.



## -syntax

````
ULONG KsGetNodeIdFromIrp(
  _In_ PIRP Irp
);
````


## -parameters

### -param Irp [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure for which to determine the associated node ID. This IRP must have been sent to a file object corresponding to a filter, pin, or node.


## -returns
<b>KsGetNodeIdFromIrp </b>returns the ID of the node to which <i>Irp </i>was submitted. If <i>Irp</i> was instead submitted directly to the filter, it returns KSFILTER_NODE.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksaddirptocancelablequeue.md">KsAddIrpToCancelableQueue</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksforwardirp.md">KsForwardIrp</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksdispatchirp.md">KsDispatchIrp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetNodeIdFromIrp function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

