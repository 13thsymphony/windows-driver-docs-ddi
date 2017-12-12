---
UID: NF.ndis.NdisResetEvent
title: NdisResetEvent function
author: windows-driver-content
description: The NdisResetEvent function clears the Signaled state of a given event.
old-location: netvista\ndisresetevent.htm
old-project: netvista
ms.assetid: fba29b92-5735-4050-b690-3c25e4f57cd1
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisResetEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisResetEvent (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisResetEvent (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisResetEvent
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Synch_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisResetEvent function



## -description
The
  <b>NdisResetEvent</b> function clears the Signaled state of a given event.



## -syntax

````
VOID NdisResetEvent(
  _In_ PNDIS_EVENT Event
);
````


## -parameters

### -param Event [in]

A pointer to an initialized event object for which the caller provided the storage.


## -returns
None


## -remarks
<b>NdisResetEvent</b> explicitly sets the state of the given event to 
    <i>not-signaled</i>.

When an event is set to the 
    <i>signaled</i> state with the 
    <a href="netvista.ndissetevent">NdisSetEvent</a> function, it remains in that
    state until an explicit call to 
    <b>NdisResetEvent</b> occurs. While an event remains in the 
    <i>signaled</i> state, callers of the 
    <a href="netvista.ndiswaitevent">NdisWaitEvent</a> function on that event are
    dispatched for execution without waiting.


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
Version

</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff554697">NdisResetEvent (NDIS 5.1)</a>) in
   Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisResetEvent (NDIS 5.1)</b>) in
   Windows XP.

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
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_synch_function">Irql_Synch_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisinitializeevent">NdisInitializeEvent</a>
</dt>
<dt>
<a href="netvista.ndissetevent">NdisSetEvent</a>
</dt>
<dt>
<a href="netvista.ndiswaitevent">NdisWaitEvent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisResetEvent function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

