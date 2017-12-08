---
UID: NF.ntddk.RtlLeftChild
title: RtlLeftChild
author: windows-driver-content
description: The RtlLeftChild routine returns a pointer to the left child of the specified splay link node.
old-location: ifsk\rtlleftchild.htm
old-project: ifsk
ms.assetid: 26e6b0c6-7de0-43c9-a117-5c0bf0e986a2
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlLeftChild
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlLeftChild
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.iface: 
---

# RtlLeftChild function



## -description
<p>The <b>RtlLeftChild</b> routine returns a pointer to the left child of the specified splay link node. </p>


## -syntax

````
PRTL_SPLAY_LINKS RtlLeftChild(
  _In_ PRTL_SPLAY_LINKS Links
);
````


## -parameters
<dl>

### -param Links [in]

<dd>
<p>Pointer to the node whose left child is to be returned. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. </p>
</dd>
</dl>

## -returns
<p><b>RtlLeftChild</b> returns a pointer to the left child of the node at <i>Links</i>, or it returns <b>NULL</b> if the specified node has no left child. </p>

## -remarks
<p><b>RtlLeftChild</b> can be called repeatedly in conjunction with <b>RtlParent</b> and <b>RtlRightChild</b> to walk a splay link tree. </p>

<p>Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. </p>

<p>Callers of <b>RtlLeftChild</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>See Remarks section.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinsertasleftchild.md">RtlInsertAsLeftChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlparent.md">RtlParent</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlrightchild.md">RtlRightChild</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlLeftChild routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
