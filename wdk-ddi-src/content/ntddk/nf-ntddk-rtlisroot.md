---
UID: NF.ntddk.RtlIsRoot
title: RtlIsRoot macro
author: windows-driver-content
description: The RtlIsRoot routine determines whether the specified node is the root node of a splay link tree.
old-location: ifsk\rtlisroot.htm
old-project: ifsk
ms.assetid: 74b3894e-972f-430b-bb8f-20fa46bf8b7d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RtlIsRoot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlIsRoot
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
---

# RtlIsRoot macro



## -description
The <b>RtlIsRoot</b> routine determines whether the specified node is the root node of a splay link tree. 



## -syntax

````
BOOLEAN RtlIsRoot(
  _In_ PRTL_SPLAY_LINKS Links
);
````


## -parameters

### -param Links [in]

Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 


## -remarks
Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlIsRoot</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the splay link tree or just-initialized node at <i>Links</i> is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
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
<a href="ifsk.rtlinitializesplaylinks">RtlInitializeSplayLinks</a>
</dt>
<dt>
<a href="ifsk.rtlisleftchild">RtlIsLeftChild</a>
</dt>
<dt>
<a href="ifsk.rtlisrightchild">RtlIsRightChild</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlIsRoot routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
