---
UID: NF.ndis.NdisMSleep
title: NdisMSleep function
author: windows-driver-content
description: The NdisMSleep function delays execution of the caller for a given interval in microseconds.
old-location: netvista\ndismsleep.htm
old-project: NetVista
ms.assetid: 5b6c3fc5-4220-4a4b-9412-8bfc8141ea90
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisMSleep
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMSleep (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisMSleep (NDIS 5.1)).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMSleep
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miniport_Driver_Function
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

# NdisMSleep function



## -description
The 
  <b>NdisMSleep</b> function delays execution of the caller for a given interval in microseconds.



## -syntax

````
VOID NdisMSleep(
  _In_ ULONG MicrosecondsToSleep
);
````


## -parameters

### -param MicrosecondsToSleep [in]

The number of microseconds to delay.


## -returns
None


## -remarks
For the given time in the 
    <i>MicrosecondsToSleep</i> parameter, the caller's thread of execution is put into a wait state, thereby
    allowing other threads to get work done on the current processor. When the given interval expires, the
    caller of 
    <b>NdisMSleep</b> resumes execution.

An NDIS driver should always call 
    <b>NdisMSleep</b> in preference to the 
    <a href="netvista.ndisstallexecution">NdisStallExecution</a> function unless the
    driver is running at IRQL &gt;= DISPATCH_LEVEL. 
    <b>NdisMSleep</b> can accept a larger delay interval than 
    <b>NdisStallExecution</b>, which should 
    <u>never</u> be called with an interval greater than 50 microseconds. Do not call <b>NdisMSleep</b> with a timeout of more than 30,000,000 microseconds (that is, 30 seconds or half a minute).

Miniport drivers can call 
    <b>NdisMSleep</b> from their 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> and,
    possibly, 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> functions when either
    function must wait for state changes to occur in the NIC before that function continues its
    operations.

Both 
    <b>NdisMSleep</b> and 
    <b>NdisStallExecution</b> allow a miniport driver to specify a delay consistently and independently of the
    clock speed of the host CPU. Neither function involves a timer object such as those that are used by the 
    <a href="netvista.ndissettimerobject">NdisSetTimerObject</a> function. The
    resolution of the host system clock varies, so very short delays can take slightly longer than the delay
    time that the caller of 
    <b>NdisMSleep</b> or 
    <b>NdisStallExecution</b> specified.


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
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff553640">NdisMSleep (NDIS 5.1)</a>) in Windows
   Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisMSleep (NDIS 5.1)</b>).

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
<a href="devtest.ndis_irql_miniport_driver_function">Irql_Miniport_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a>
</dt>
<dt>
<a href="netvista.ndissettimerobject">NdisSetTimerObject</a>
</dt>
<dt>
<a href="netvista.ndisstallexecution">NdisStallExecution</a>
</dt>
<dt>
<a href="netvista.ndiswaitevent">NdisWaitEvent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisMSleep function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

