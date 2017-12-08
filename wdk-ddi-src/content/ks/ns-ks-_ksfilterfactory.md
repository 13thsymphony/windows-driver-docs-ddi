---
UID: NS.KS._KSFILTERFACTORY
title: _KSFILTERFACTORY
author: windows-driver-content
description: The KSFILTERFACTORY structure represents a filter factory.
old-location: stream\ksfilterfactory.htm
old-project: stream
ms.assetid: c40e25f8-e6e5-43bc-895d-a6b247d07470
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _KSFILTERFACTORY, KSFILTERFACTORY, *PKSFILTERFACTORY
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
req.alt-api: KSFILTERFACTORY
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

# _KSFILTERFACTORY structure



## -description
The KSFILTERFACTORY structure represents a filter factory.


## -syntax

````
typedef struct _KSFILTERFACTORY {
  const KSFILTER_DESCRIPTOR *FilterDescriptor;
  KSOBJECT_BAG              Bag;
  PVOID                     Context;
} KSFILTERFACTORY, *PKSFILTERFACTORY;
````


## -struct-fields

### -field FilterDescriptor

A pointer to a <a href="stream.ksfilter_descriptor">KSFILTER_DESCRIPTOR</a> structure that describes the characteristics of filters created by this factory.

### -field Bag

This member specifies the KSOBJECT_BAG (equivalent to type PVOID) associated with this filter factory. Object bags are structures used to associate dynamic memory with a specific AVStream object. Anything in the filter factory object bag is automatically cleaned up when the filter factory is deleted. See the conceptual section on <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a> for more information.

### -field Context

A pointer to a memory address that the client may use to associate context information with the filter factory. AVStream does not use this member in any way. Note that any dynamic memory associated with the filter factory should be placed in the object bag with <b>KsAddItemToObjectBag</b>. <b>Context</b> is initialized to the value of the <b>Context</b> member of the parent <a href="stream.ksdevice">KSDEVICE</a> at the time the factory is created. See <a href="https://msdn.microsoft.com/b7d6f06d-6c97-414e-a453-d375e2d7ccf5">AVStream Object Hierarchy</a>.

## -remarks
A filter factory explicitly represents a device's ability to instantiate a given type of filter as described by a filter descriptor.

Drivers for hardware typically use this structure to manage a particular function of the hardware that is exposed as a type of filter. Software filters generally do not need to manage the device at this level.

Filter factory objects are created in two ways. They can be created during the AddDevice processing as indicated by the device descriptor's list of filter descriptors. They can also be created explicitly by the client in a call to <a href="stream.kscreatefilterfactory">KsCreateFilterFactory</a>. The client may create filter factories at any time, but this is typically done during the processing of the PnP start IRP when an evaluation of assigned resources indicates what types of filters must be exposed by the device.

For the purposes of synchronization, the lifetime of filter factories created implicitly is defined as the interval starting when the client's device create dispatch function is (or would be) called and ending after the client's device PnP remove dispatch function is (or would be) called. The lifetime of filter factories created explicitly by calling <a href="stream.kscreatefilterfactory">KsCreateFilterFactory</a> starts immediately after that call returns.

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
<a href="stream.kscreatefilterfactory">KsCreateFilterFactory</a>
</dt>
<dt>
<a href="stream.ksadditemtoobjectbag">KsAddItemToObjectBag</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSFILTERFACTORY structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
