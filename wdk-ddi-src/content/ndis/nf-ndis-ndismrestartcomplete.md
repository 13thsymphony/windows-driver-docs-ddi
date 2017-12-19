---
UID: NF.ndis.NdisMRestartComplete
title: NdisMRestartComplete function
author: windows-driver-content
description: A miniport driver must call the NdisMRestartComplete function to complete a restart operation if the driver returned NDIS_STATUS_PENDING from its MiniportRestart function.
old-location: netvista\ndismrestartcomplete.htm
old-project: NetVista
ms.assetid: f43137ed-2ea3-4b7c-8d61-bda76bcb5f34
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisMRestartComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMRestartComplete
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
req.irql: <= DISPATCH_LEVEL
---

# NdisMRestartComplete function



## -description
A miniport driver must call the 
  <b>NdisMRestartComplete</b> function to complete a restart operation if the driver returned
  NDIS_STATUS_PENDING from its 
  <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> function.



## -syntax

````
VOID NdisMRestartComplete(
  _In_ NDIS_HANDLE MiniportAdapterHandle,
  _In_ NDIS_STATUS Status
);
````


## -parameters

### -param MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


### -param Status [in]

The final status of the restart operation. The following status values are supported:
     




### -param NDIS_STATUS_SUCCESS

The driver successfully restarted the flow of network data through the miniport adapter.


### -param NDIS_STATUS_RESOURCES

The restart failed because of insufficient resources.


### -param NDIS_STATUS_FAILURE

The driver indicates NDIS_STATUS_FAILURE if none of the preceding values applies. The driver
       should call the 
       <a href="netvista.ndiswriteerrorlogentry">NdisWriteErrorLogEntry</a> function
       with parameters that specify the reason for the failure.

</dd>
</dl>

## -returns
None


## -remarks
The miniport adapter specified at 
    <i>MiniportAdapterHandle</i> enters the 
    <i>Restarting</i> state when NDIS calls the 
    <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> function.

After the miniport driver successfully restarts the send and receive operations for the miniport
    adapter, the driver must complete the pending restart operation. The pending restart operation is
    complete after the driver calls 
    <b>NdisMRestartComplete</b>. The miniport adapter is in the 
    <i>Running</i> state after the restart operation is complete.

A miniport driver can resume indicating received packets immediately after NDIS calls 
    <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> and before the driver calls 
    <b>NdisMRestartComplete</b>. The driver should be ready to accept send requests after it completes the
    restart request.


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
Supported in NDIS 6.0 and later.

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
<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a>
</dt>
<dt>
<a href="netvista.ndiswriteerrorlogentry">NdisWriteErrorLogEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisMRestartComplete function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

