---
UID: NF.ks.KsCreateTopologyNode
title: KsCreateTopologyNode function
author: windows-driver-content
description: The KsCreateTopologyNode function creates a handle to a topology node instance. The function can only be called at PASSIVE_LEVEL.
old-location: stream\kscreatetopologynode.htm
old-project: stream
ms.assetid: aeed8086-b413-428c-b275-d555523b5503
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsCreateTopologyNode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsCreateTopologyNode
req.alt-loc: ks.lib,ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
---

# KsCreateTopologyNode function



## -description
The <b>KsCreateTopologyNode</b> function creates a handle to a topology node instance. The function can only be called at <b>PASSIVE_LEVEL</b>.



## -syntax

````
NTSTATUS KsCreateTopologyNode(
  _In_  HANDLE         ParentHandle,
  _In_  PKSNODE_CREATE NodeCreate,
  _In_  ACCESS_MASK    DesiredAccess,
  _Out_ PHANDLE        NodeHandle
);
````


## -parameters

### -param ParentHandle [in]

Specifies the handle to the parent on which the node is created.


### -param NodeCreate [in]

Specifies topology node create parameters.


### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> indicating the desired access to the object. This is typically <b>GENERIC_READ</b> and/or <b>GENERIC_WRITE</b>.


### -param NodeHandle [out]

Location for the topology node handle.


## -returns
Returns <b>STATUS_SUCCESS</b>, or an error if unable to create a node. 


## -remarks
The <a href="..\ks\ns-ks-ksnode_create.md">KSNODE_CREATE</a> structure describes the set of information used to create the node handle.


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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksnode_create.md">KSNODE_CREATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCreateTopologyNode function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

