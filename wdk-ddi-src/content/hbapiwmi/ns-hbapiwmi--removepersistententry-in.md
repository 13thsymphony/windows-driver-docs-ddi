---
UID: NS.hbapiwmi._RemovePersistentEntry_IN
title: RemovePersistentEntry_IN
author: windows-driver-content
description: The RemovePersistentEntry_IN structure is used by a WMI client to deliver input parameter data to the RemovePersistentEntry WMI method.
old-location: storage\removepersistententry_in.htm
old-project: storage
ms.assetid: 7019ee37-2080-4ba3-ba39-977e575ec04e
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: RemovePersistentEntry_IN, RemovePersistentEntry_IN, *PRemovePersistentEntry_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RemovePersistentEntry_IN
req.alt-loc: hbapiwmi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# RemovePersistentEntry_IN structure



## -description
<p>The RemovePersistentEntry_IN structure is used by a WMI client to deliver input parameter data to the <a href="storage.removepersistententry">RemovePersistentEntry</a> WMI method.</p>


## -syntax

````
typedef struct _RemovePersistentEntry_IN {
  UCHAR               PortWWN[8];
  HBAFCPBindingEntry2 Binding;
} RemovePersistentEntry_IN, *PRemovePersistentEntry_IN;
````


## -struct-fields
<dl>

### -field PortWWN

<dd>
<p>Contains a worldwide name that indicates the port for which a persistent binding will be removed. </p>
</dd>

### -field Binding

<dd>
<p>Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi--hbafcpbindingentry2.md">HBAFCPBindingEntry2</a> that indicates the binding to be removed from the indicated port's list of bindings. </p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the RemovePersistentEntry_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="storage.msfc_hbafcpinfo_wmi_class">MSFC_HBAFCPInfo WMI Class</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.removepersistententry">RemovePersistentEntry</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemovePersistentEntry_IN structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
