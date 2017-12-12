---
UID: NS.KS._KSFILTER
title: _KSFILTER
author: windows-driver-content
description: The KSFILTER structure describes an instantiated filter.
old-location: stream\ksfilter.htm
old-project: stream
ms.assetid: b9233f69-1ddf-4133-afd3-150aef5fc4a0
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _KSFILTER, *PKSFILTER, KSFILTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSFILTER
req.alt-loc: ks.h
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
---

# _KSFILTER structure



## -description
The KSFILTER structure describes an instantiated filter.



## -syntax

````
typedef struct _KSFILTER {
  const KSFILTER_DESCRIPTOR *Descriptor;
  KSOBJECT_BAG              Bag;
  PVOID                     Context;
} KSFILTER, *PKSFILTER;
````


## -struct-fields

### -field Descriptor

A pointer to a <a href="stream.ksfilter_descriptor">KSFILTER_DESCRIPTOR</a> structure that describes the characteristics of this particular filter.


### -field Bag

This member specifies the KSOBJECT_BAG (equivalent to type PVOID) associated with this filter instance. <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a> are structures used to associate dynamic memory with a specific AVStream object. Anything in the filter object bag is automatically cleaned up when the filter is deleted.


### -field Context

A pointer that is used by the client to associate context information with the specific filter instance. Typically, such context information is associated in the filter's <b>Create</b> member as defined in the KSFILTER_DISPATCH table for this filter instance. Any dynamically allocated context information should be placed in the object bag with <a href="stream.ksadditemtoobjectbag">KsAddItemToObjectBag</a>. <b>Context</b> is initialized to the value of the <b>Context</b> member of the parent <a href="stream.ksfilterfactory">KSFILTERFACTORY</a> at the time the filter is created. See <a href="https://msdn.microsoft.com/b7d6f06d-6c97-414e-a453-d375e2d7ccf5">AVStream Object Hierarchy</a>.


## -remarks
Drivers implementing software filters typically associate filter state with the KSFILTER structure. Software filters usually process data within the callback specified by the <b>Process</b> member of the corresponding <a href="stream.ksfilter_dispatch">KSFILTER_DISPATCH</a> structure.

Hardware filters typically do not use KSFILTER because the focus of the hardware driver is the platform transition: the movement of data between the host and the external hardware. This transition is typically handled by code associated with an AVStream queue object.

Also see <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.

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
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>
</dt>
<dt>
<a href="stream.ksfilter_dispatch">KSFILTER_DISPATCH</a>
</dt>
<dt>
<a href="stream.kscompletependingrequest">KsCompletePendingRequest</a>
</dt>
<dt>
<a href="stream.ksadditemtoobjectbag">KsAddItemToObjectBag</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSFILTER structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

