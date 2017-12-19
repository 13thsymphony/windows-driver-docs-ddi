---
UID: NF.ndis.NdisMRemoveMiniport
title: NdisMRemoveMiniport function
author: windows-driver-content
description: The NdisMRemoveMiniport function removes the specified miniport driver adapter that the miniport driver has determined is unrecoverable from the system.
old-location: netvista\ndismremoveminiport.htm
old-project: NetVista
ms.assetid: 70745b03-f9a3-4398-b41a-dc75bd16ffe0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisMRemoveMiniport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 5.1, and NDIS 6.0 and later. For NDIS 5.1 drivers, see    NdisMRemoveMiniport (NDIS   5.1).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMRemoveMiniport
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

# NdisMRemoveMiniport function



## -description
The
  <b>NdisMRemoveMiniport</b> function removes the specified miniport driver adapter that the miniport driver
  has determined is unrecoverable from the system.



## -syntax

````
NDIS_STATUS NdisMRemoveMiniport(
  _In_ NDIS_HANDLE MiniportAdapterHandle
);
````


## -parameters

### -param MiniportAdapterHandle [in]

The handle to the initialized miniport adapter that the miniport driver has determined is
     unrecoverable.


## -returns
<b>NdisMRemoveMiniport</b> can return either of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The miniport adapter has been removed.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>An attempt to remove the miniport adapter failed.

 


## -remarks
If a miniport driver has determined that a particular miniport adapter has failed and is
    unrecoverable, the miniport driver can call 
    <b>NdisMRemoveMiniport</b> to remove the miniport adapter from the local computer system. In this call,
    the miniport driver passes the handle to the miniport adapter to remove.

For example, if a miniport driver detects that a miniport adapter is resetting very frequently and is
    causing the computer to freeze every few seconds, the driver can request NDIS to remove the miniport
    adapter.


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
   <a href="https://msdn.microsoft.com/1438603b-107f-4173-bbb1-90935ab7811d">NdisMRemoveMiniport (NDIS
   5.1)</a>.

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