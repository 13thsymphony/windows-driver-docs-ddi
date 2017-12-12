---
UID: NF.ks.KsFilterCreateNode
title: KsFilterCreateNode function
author: windows-driver-content
description: The KsFilterCreateNode function creates a new topology node on the specified filter.
old-location: stream\ksfiltercreatenode.htm
old-project: stream
ms.assetid: 2a796bb9-7d55-47da-9a57-2829cd193e23
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsFilterCreateNode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsFilterCreateNode
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
req.irql: PASSIVE_LEVEL
---

# KsFilterCreateNode function



## -description
The<b> KsFilterCreateNode</b> function creates a new topology node on the specified filter.



## -syntax

````
KSDDKAPI NTSTATUS NTAPI KsFilterCreateNode(
  _In_        PKSFILTER         Filter,
  _In_  const KSNODE_DESCRIPTOR *NodeDescriptor,
  _Out_       PULONG            NodeID
);
````


## -parameters

### -param Filter [in]

A pointer to a <a href="stream.ksfilter">KSFILTER</a> structure on which to create a new topology node.


### -param NodeDescriptor [in]

A pointer to a <a href="stream.ksnode_descriptor">KSNODE_DESCRIPTOR</a> structure that describes the new node.


### -param NodeID [out]

A pointer to a ULONG where AVStream places the ID of the new node.


## -returns
<b>KsFilterCreateNode</b>  returns the success or failure of creating the node. The call may fail because of invalid parameters, low memory, or other reasons.


## -remarks
Note that the filter control mutex must be held before calling this function. For more information, see <a href="https://msdn.microsoft.com/402795a0-e567-4e7e-a7d8-b2ce29ffb8fd">Filter Control Mutex in AVStream</a>.


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
<dt>Ks.h</dt>
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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksfiltercreatepinfactory">KsFilterCreatePinFactory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterCreateNode function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

