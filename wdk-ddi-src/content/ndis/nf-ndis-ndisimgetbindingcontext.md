---
UID: NF.ndis.NdisIMGetBindingContext
title: NdisIMGetBindingContext function
author: windows-driver-content
description: The NdisIMGetBindingContext function allows an NDIS protocol driver to access the device context area, which was created by an underlying intermediate driver, for a virtual miniport to which the higher level protocol driver is bound.
old-location: netvista\ndisimgetbindingcontext.htm
old-project: NetVista
ms.assetid: fc0668b3-9242-4d30-9dc9-820f6d596d6c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisIMGetBindingContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisIMGetBindingContext (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisIMGetBindingContext (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisIMGetBindingContext
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_IM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: < DISPATCH_LEVEL
---

# NdisIMGetBindingContext function



## -description
The 
  <b>NdisIMGetBindingContext</b> function allows an NDIS protocol driver to access the device context area,
  which was created by an underlying intermediate driver, for a virtual miniport to which the higher level
  protocol driver is bound.



## -syntax

````
NDIS_HANDLE NdisIMGetBindingContext(
  _In_ NDIS_HANDLE NdisBindingHandle
);
````


## -parameters

### -param NdisBindingHandle [in]

The binding handle that the 
     <a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a> function returned at
     the 
     <i>NdisBindingHandle</i> parameter that identifies the virtual miniport of the next lower intermediate
     driver to which the caller is bound.


## -returns
<b>NdisIMGetBindingContext</b> returns a handle to the device context area for the given virtual
     miniport, or it returns <b>NULL</b> if no such context area exists.


## -remarks
A protocol driver or intermediate driver can call 
    <b>NdisIMGetBindingContext</b> from its 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function to
    access the device context for a virtual miniport to which it is bound. The device context provides a
    common context area for all overlying protocol drivers that are bound to the same underlying intermediate
    driver.

Such a device context area was allocated and defined by the lower level NDIS intermediate driver and
    passed to NDIS in a call to the 
    <a href="netvista.ndisiminitializedeviceinstanceex">
    NdisIMInitializeDeviceInstanceEx</a> function.

All protocol drivers that call 
    <b>NdisIMGetBindingContext</b> can safely assume that the underlying intermediate driver allocated its
    context area from nonpaged pool. They should treat the returned context area as read-only, preserving the
    state set up by the underlying NDIS intermediate driver that defined it.


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
Version

</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/9a12b473-c54b-44de-9594-6c4f4f47f223">NdisIMGetBindingContext (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisIMGetBindingContext (NDIS
   5.1)</b>) in Windows XP.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt; DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_im_function">Irql_IM_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisiminitializedeviceinstanceex">
   NdisIMInitializeDeviceInstanceEx</a>
</dt>
<dt>
<a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisIMGetBindingContext function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

