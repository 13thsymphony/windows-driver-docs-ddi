---
UID: NF.ntddk.RtlInsertAsRightChild
title: RtlInsertAsRightChild
author: windows-driver-content
description: The RtlInsertAsRightChild routine inserts a given splay link into the tree as the right child of a given node in that tree.
old-location: ifsk\rtlinsertasrightchild.htm
old-project: ifsk
ms.assetid: eaeff5fe-a678-44e5-a78d-ef4816708878
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlInsertAsRightChild
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
req.alt-api: RtlInsertAsRightChild
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

# RtlInsertAsRightChild function



## -description
<p>The <b>RtlInsertAsRightChild</b> routine inserts a given splay link into the tree as the right child of a given node in that tree. </p>


## -syntax

````
VOID RtlInsertAsRightChild(
  _In_ PRTL_SPLAY_LINKS ParentLinks,
  _In_ PRTL_SPLAY_LINKS ChildLinks
);
````


## -parameters
<dl>

### -param ParentLinks [in]

<dd>
<p>Pointer to the node in the tree at which <i>ChildLinks</i> should be inserted as the right child. </p>
</dd>

### -param ChildLinks [in]

<dd>
<p>Pointer to the splay link node to be inserted into the tree. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Callers of <b>RtlInsertAsRightChild</b> are responsible for meeting the following criteria:</p>

<p>The node at <i>ParentLinks</i> must have no right child. </p>

<p>A caller can determine whether the node already has a right child by calling <b>RtlRightChild</b>. If <b>RtlRightChild</b> returns <b>NULL</b>, <i>ParentLinks</i> is a valid parameter to <b>RtlInsertAsRightChild</b>.</p>

<p>The node at <i>ChildLinks</i> must have no parent.</p>

<p>A caller can determine whether this node already has a parent by calling <b>RtlIsRoot</b> or <b>RtlParent</b>. If <b>RtlIsRoot</b> returns <b>TRUE</b> when called with <i>ChildLinks</i>, <i>ChildLinks</i> is a valid parameter to <b>RtlInsertAsRightChild</b>. If <b>RtlParent</b> returns an equivalent pointer to <i>ChildLinks</i>, <i>ChildLinks</i> is also a valid parameter to <b>RtlInsertAsRightChild</b>. </p>

<p>Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. </p>

<p>Callers of <b>RtlInsertAsRightChild</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the splay link tree and <i>ChildLinks</i> node are nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. </p>

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
<a href="..\ntddk\nf-ntddk-rtlisroot.md">RtlIsRoot</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlrightchild.md">RtlRightChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlparent.md">RtlParent</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlsplay.md">RtlSplay</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlInsertAsRightChild routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
