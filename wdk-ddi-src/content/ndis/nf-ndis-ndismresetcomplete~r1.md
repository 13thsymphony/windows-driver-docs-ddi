---
UID: NF.ndis.NdisMResetComplete~r1
title: NdisMResetComplete macro
author: windows-driver-content
description: The NdisMResetComplete function returns the final status of a reset request for which the miniport driver previously returned NDIS_STATUS_PENDING.
old-location: netvista\ndismresetcomplete.htm
old-project: NetVista
ms.assetid: 3da12a14-a90a-46a6-b67e-55044fdc3ca1
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisMResetComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 5.1, and NDIS 6.0 and later. For NDIS 5.1 drivers, see    NdisMResetComplete (NDIS 5.1).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMResetComplete
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
---

# NdisMResetComplete macro



## -description
The 
  <b>NdisMResetComplete</b> function returns the final status of a reset request for which the miniport driver
  previously returned NDIS_STATUS_PENDING.



## -syntax

````
VOID NdisMResetComplete(
  _In_ NDIS_HANDLE MiniportAdapterHandle,
  _In_ NDIS_STATUS Status,
  _In_ BOOLEAN     AddressingReset
);
````


## -parameters

### -param MiniportAdapterHandle [in]

The miniport adapter handle that NDIS originally passed to the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.


### -param Status [in]

The final status of the reset operation just completed


### -param AddressingReset [in]

A Boolean value that is <b>TRUE</b> if NDIS is responsible for restoring the settings for multicast
     addresses, packet filters, and task offload information. In this case, the miniport driver is
     responsible for restoring the rest of the configuration settings for the network interface card (NIC)
     referenced by 
     <i>MiniportAdapterHandle</i> . 
     

If 
     <i>AddressingReset</i> is <b>FALSE</b>, the miniport driver is responsible for restoring all of the
     configuration settings for the NIC.

For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff546572">Hardware Reset</a>.


## -remarks
If the 
    <a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a> function returns
    NDIS_STATUS_PENDING, the miniport driver must call 
    <b>NdisMResetComplete</b> when it completes the reset operation.

Protocol drivers cannot initiate a reset operation in NDIS 6.0 and later versions.

Some NICs lose all multicast address, packet filter, or functional address information when a soft
    reset is issued. The driver of such a NIC sets 
    <i>AddressingReset</i> to <b>TRUE</b> when it calls 
    <b>NdisMResetComplete</b>, causing NDIS to call its 
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function to
    restore the addressing state. For more information, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff546572">Hardware Reset</a>.

A miniport driver must release any spin lock that it is holding before calling 
    <b>NdisMResetComplete</b>.

In NDIS 6.0 and later, callers of 
    <b>NdisMResetComplete</b> must run at IRQL &lt;= DISPATCH_LEVEL. Otherwise, callers of 
    <b>NdisMResetComplete</b> must run at IRQL = DISPATCH_LEVEL.


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
Supported in NDIS 5.1, and NDIS 6.0 and later. For NDIS 5.1 drivers, see 
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff553612">NdisMResetComplete (NDIS 5.1)</a>.

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
&lt;= DISPATCH_LEVEL (see Remarks section)

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
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisMResetComplete function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

