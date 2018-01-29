---
UID : NF:ndis.NdisMCmRegisterAddressFamilyEx
title : NdisMCmRegisterAddressFamilyEx function
author : windows-driver-content
description : The NdisMCmRegisterAddressFamilyEx function registers an address family (AF) for communication between a miniport call manager (MCM) and CoNDIS clients.
old-location : netvista\ndismcmregisteraddressfamilyex.htm
old-project : netvista
ms.assetid : f58a9c08-d2cf-48d1-98d1-68aecd3b7bd0
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : condis_mcm_ref_9e0ef0aa-0fa8-4f40-a225-8908099356bc.xml, NdisMCmRegisterAddressFamilyEx, ndis/NdisMCmRegisterAddressFamilyEx, netvista.ndismcmregisteraddressfamilyex, NdisMCmRegisterAddressFamilyEx function [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_MCM_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisMCmRegisterAddressFamilyEx function
The
  <b>NdisMCmRegisterAddressFamilyEx</b> function registers an address family (AF) for communication between a
  miniport call manager (MCM) and CoNDIS clients.

## Syntax

````
NDIS_STATUS NdisMCmRegisterAddressFamilyEx(
  _In_ NDIS_HANDLE        MiniportAdapterHandle,
  _In_ PCO_ADDRESS_FAMILY AddressFamily
);
````

## Parameters

`MiniportAdapterHandle`

An NDIS-supplied handle that identifies a miniport adapter. This handle is an input parameter to
     the MCM's 
     <mshelp:link keywords="netvista.miniportinitializeex" tabindex="0"><i>
     MiniportInitializeEx</i></mshelp:link> function.

`AddressFamily`

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545368">CO_ADDRESS_FAMILY</a> structure that identifies
     the AF that the MCM driver supports. 
     

The pointer becomes an input parameter to the 
     <mshelp:link keywords="netvista.protocolcoafregisternotify" tabindex="0"><i>
     ProtocolCoAfRegisterNotify</i></mshelp:link> functions of all of the CoNDIS clients that are bound to this MCM
     driver.


## Return Value

<b>NdisMCmRegisterAddressFamilyEx</b> can return any of the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver registered with NDIS as a call manager for the AF that the 
       <i>AddressFamily</i> parameter specified, so NDIS will call the 
       <mshelp:link keywords="netvista.protocolcoafregisternotify" tabindex="0"><i>
       ProtocolCoAfRegisterNotify</i></mshelp:link> functions of all of the clients that bind to the MCM driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The requested operation failed because NDIS could not allocate sufficient memory or initialize
       the state information that it uses to track the MCM driver as a call manager of the specified
       AF.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
NDIS failed the call to 
       <b>NdisMCmRegisterAddressFamilyEx</b>, possibly for one of the following reasons:
       

<ul>
<li>
The caller was not registered as a connection-oriented miniport driver.

</li>
<li>
The caller tried to register a duplicate AF for a given miniport adapter.

</li>
</ul>
</td>
</tr>
</table>

## Remarks

NDIS MCMs, which register as NDIS miniport drivers by calling the 
    <mshelp:link keywords="netvista.ndismregisterminiportdriver" tabindex="0"><b>
    NdisMRegisterMiniportDriver</b></mshelp:link> function, should call the 
    <b>NdisMCmRegisterAddressFamilyEx</b> function to register an AF. Stand-alone call managers should instead
    call the 
    <mshelp:link keywords="netvista.ndiscmregisteraddressfamilyex" tabindex="0"><b>
    NdisCmRegisterAddressFamilyEx</b></mshelp:link> function.

To register an AF for a miniport adapter, the MCM should call 
    <b>NdisMCmRegisterAddressFamilyEx</b> from the 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.

The driver of any network interface card (NIC) that has on-board connection-oriented signaling support
    can register itself as an MCM driver for better performance in managing calls. If a driver registers as
    an MCM driver, any stand-alone call manager with the NIC driver's own call-management support is
    displaced.

An MCM driver calls 
    <b>NdisMCmRegisterAddressFamilyEx</b> after it has determined that a NIC is fully operational and the
    driver can complete network I/O operations. That is, such an MCM registers itself as a call manager and
    advertises its specific signaling services for CoNDIS clients.

After 
    <i>MiniportInitializeEx</i> returns control with a successful registration as a call manager, NDIS calls
    the 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> functions
    of potential clients and, then, the 
    <mshelp:link keywords="netvista.protocolcoafregisternotify" tabindex="0"><i>
    ProtocolCoAfRegisterNotify</i></mshelp:link> functions of all of the clients that bind themselves to the associated
    MCM miniport adapter. These clients then cause NDIS to call the 
    <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function of the
    MCM.

An MCM can support more than one AF for a single NIC that it manages. The MCM driver must call 
    <b>NdisMCmRegisterAddressFamilyEx</b> once for each AF that it registers for a miniport adapter. Only one
    MCM driver can support a particular type of AF for clients that are bound to a given miniport
    adapter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_MCM_Function |

## See Also

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>

<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>

<a href="..\ndis\nc-ndis-protocol_co_oid_request.md">ProtocolCoOidRequest</a>

<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>

<mshelp:link keywords="netvista.ndiscmregisteraddressfamilyex" tabindex="0"><b>
   NdisCmRegisterAddressFamilyEx</b></mshelp:link>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545368">CO_ADDRESS_FAMILY</a>

<mshelp:link keywords="netvista.protocolcooidrequestcomplete" tabindex="0"><i>
   ProtocolCoOidRequestComplete</i></mshelp:link>

<a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">ProtocolCoAfRegisterNotify</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmRegisterAddressFamilyEx function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>