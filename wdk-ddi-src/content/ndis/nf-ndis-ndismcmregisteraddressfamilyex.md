---
UID: NF.ndis.NdisMCmRegisterAddressFamilyEx
title: NdisMCmRegisterAddressFamilyEx function
author: windows-driver-content
description: The NdisMCmRegisterAddressFamilyEx function registers an address family (AF) for communication between a miniport call manager (MCM) and CoNDIS clients.
old-location: netvista\ndismcmregisteraddressfamilyex.htm
old-project: netvista
ms.assetid: f58a9c08-d2cf-48d1-98d1-68aecd3b7bd0
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisMCmRegisterAddressFamilyEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCmRegisterAddressFamilyEx
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_MCM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NdisMCmRegisterAddressFamilyEx function



## -description
The
  <b>NdisMCmRegisterAddressFamilyEx</b> function registers an address family (AF) for communication between a
  miniport call manager (MCM) and CoNDIS clients.


## -syntax

````
NDIS_STATUS NdisMCmRegisterAddressFamilyEx(
  _In_ NDIS_HANDLE        MiniportAdapterHandle,
  _In_ PCO_ADDRESS_FAMILY AddressFamily
);
````


## -parameters

### -param MiniportAdapterHandle [in]

An NDIS-supplied handle that identifies a miniport adapter. This handle is an input parameter to
     the MCM's 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.

### -param AddressFamily [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545368">CO_ADDRESS_FAMILY</a> structure that identifies
     the AF that the MCM driver supports. 
     
The pointer becomes an input parameter to the 
     <a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">
     ProtocolCoAfRegisterNotify</a> functions of all of the CoNDIS clients that are bound to this MCM
     driver.

## -returns
<b>NdisMCmRegisterAddressFamilyEx</b> can return any of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The miniport driver registered with NDIS as a call manager for the AF that the 
       <i>AddressFamily</i> parameter specified, so NDIS will call the 
       <a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">
       ProtocolCoAfRegisterNotify</a> functions of all of the clients that bind to the MCM driver.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>The requested operation failed because NDIS could not allocate sufficient memory or initialize
       the state information that it uses to track the MCM driver as a call manager of the specified
       AF.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>NDIS failed the call to 
       <b>NdisMCmRegisterAddressFamilyEx</b>, possibly for one of the following reasons:
       

The caller was not registered as a connection-oriented miniport driver.

The caller tried to register a duplicate AF for a given miniport adapter.

 

## -remarks
NDIS MCMs, which register as NDIS miniport drivers by calling the 
    <a href="netvista.ndismregisterminiportdriver">
    NdisMRegisterMiniportDriver</a> function, should call the 
    <b>NdisMCmRegisterAddressFamilyEx</b> function to register an AF. Stand-alone call managers should instead
    call the 
    <a href="netvista.ndiscmregisteraddressfamilyex">
    NdisCmRegisterAddressFamilyEx</a> function.

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
    <a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">
    ProtocolCoAfRegisterNotify</a> functions of all of the clients that bind themselves to the associated
    MCM miniport adapter. These clients then cause NDIS to call the 
    <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function of the
    MCM.

An MCM can support more than one AF for a single NIC that it manages. The MCM driver must call 
    <b>NdisMCmRegisterAddressFamilyEx</b> once for each AF that it registers for a miniport adapter. Only one
    MCM driver can support a particular type of AF for clients that are bound to a given miniport
    adapter.

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
PASSIVE_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.ndis_irql_mcm_function">Irql_MCM_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545368">CO_ADDRESS_FAMILY</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.ndiscmregisteraddressfamilyex">
   NdisCmRegisterAddressFamilyEx</a>
</dt>
<dt>
<a href="netvista.ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">ProtocolCoAfRegisterNotify</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_oid_request.md">ProtocolCoOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
   ProtocolCoOidRequestComplete</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmRegisterAddressFamilyEx function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
