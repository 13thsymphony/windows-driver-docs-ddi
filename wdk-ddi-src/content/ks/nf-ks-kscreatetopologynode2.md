---
UID: NF.ks.KsCreateTopologyNode2
title: KsCreateTopologyNode2 function
author: windows-driver-content
description: Creates a handle to a topology node instance.
old-location: stream\kscreatetopologynode2.htm
old-project: stream
ms.assetid: 71a45396-0b23-4a20-a4f4-25355a1f6271
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsCreateTopologyNode2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsCreateTopologyNode2
req.alt-loc: Ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# KsCreateTopologyNode2 function



## -description
Creates a handle to a topology node instance.
Supported starting in Windows 8.


## -syntax

````
KSDDKAPI HRESULT WINAPI KsCreateTopologyNode2(
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

A <a href="stream.ksnode_create">KSNODE_CREATE</a> structure that describes the set of information that is used to create the topology node handle.

### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> indicating the desired access to the object. This is typically <b>GENERIC_READ</b> and/or <b>GENERIC_WRITE</b>.

### -param NodeHandle [out]

Location for the topology node handle.

## -returns
Returns <b>NOERROR</b> if successful; otherwise, returns an error code.

## -remarks
This is a new version of the <a href="stream.kscreatetopologynode">KsCreateTopologyNode</a> function and uses the device broker to create the handle to the kernel streaming object. In addition, the Component Object Model (COM) <a href="com.coinitialize">CoInitialize</a> function must be called before this function is called.

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012
</td>
</tr>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="com.coinitialize">CoInitialize</a>
</dt>
<dt>
<a href="stream.kscreatetopologynode">KsCreateTopologyNode</a>
</dt>
<dt>
<a href="stream.ksnode_create">KSNODE_CREATE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCreateTopologyNode2 function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
