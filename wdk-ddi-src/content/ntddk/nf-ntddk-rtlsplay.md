---
UID: NF.ntddk.RtlSplay
title: RtlSplay function
author: windows-driver-content
description: The RtlSplay routine rebalances, or &#0034;splays,&#0034; a splay link tree around the specified splay link, making that link the new root of the tree.
old-location: ifsk\rtlsplay.htm
old-project: ifsk
ms.assetid: b62834ec-6100-429a-b62f-7e30c58b13e5
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlSplay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlSplay
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
---

# RtlSplay function



## -description
The <b>RtlSplay</b> routine rebalances, or "splays," a splay link tree around the specified splay link, making that link the new root of the tree.



## -syntax

````
PRTL_SPLAY_LINKS RtlSplay(
  _Inout_ PRTL_SPLAY_LINKS Links
);
````


## -parameters

### -param Links [in, out]

A pointer to the node that is to become the root node of the rebalanced splay link tree. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 


## -returns
<b>RtlSplay</b> returns the <i>Links</i> pointer when it has rebalanced the tree. 


## -remarks
If L is the given link, P is its parent node, and G is its grandparent node, <b>RtlSplay</b> rebalances a splay link tree according to one of the six patterns shown in the following figure.

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlSplay</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 


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
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
See Remarks section.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.rtldelete">RtlDelete</a>
</dt>
<dt>
<a href="ifsk.rtlinitializesplaylinks">RtlInitializeSplayLinks</a>
</dt>
<dt>
<a href="ifsk.rtlinsertasleftchild">RtlInsertAsLeftChild</a>
</dt>
<dt>
<a href="ifsk.rtlinsertasrightchild">RtlInsertAsRightChild</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlSplay routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

