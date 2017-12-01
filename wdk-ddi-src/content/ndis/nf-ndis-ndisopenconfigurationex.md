---
UID: NF.ndis.NdisOpenConfigurationEx
title: NdisOpenConfigurationEx
author: windows-driver-content
description: NDIS drivers call the NdisOpenConfigurationEx function to get a configuration handle that allows access to configuration parameters in the registry.
old-location: netvista\ndisopenconfigurationex.htm
old-project: netvista
ms.assetid: 76539106-6d8d-4a80-9c74-a6a4ca37c40e
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NdisOpenConfigurationEx
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
req.alt-api: NdisOpenConfigurationEx
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function, NdisOpenConfigurationEx
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# NdisOpenConfigurationEx function



## -description
<p>NDIS drivers call the 
  <b>NdisOpenConfigurationEx</b> function to get a configuration handle that allows access to configuration
  parameters in the registry.</p>


## -syntax

````
NDIS_STATUS NdisOpenConfigurationEx(
  _In_  PNDIS_CONFIGURATION_OBJECT ConfigObject,
  _Out_ PNDIS_HANDLE               ConfigurationHandle
);
````


## -parameters
<dl>

### -param <i>ConfigObject</i> [in]

<dd>
<p>A pointer to a caller-supplied and initialized 
     <a href="..\ndis\ns-ndis--ndis-configuration-object.md">
     NDIS_CONFIGURATION_OBJECT</a> structure.</p>
</dd>

### -param <i>ConfigurationHandle</i> [out]

<dd>
<p>A pointer to a caller-supplied variable in which 
     <b>NdisOpenConfigurationEx</b> returns a handle to a registry key. The registry key identifies the
     configuration parameters.</p>
</dd>
</dl>

## -returns
<p><b>NdisOpenConfigurationEx</b> returns one of the following status values:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p><b>NdisOpenConfigurationEx</b> successfully opened the registry key where the driver's configuration
       parameters are stored.</p><dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><p><b>NdisOpenConfigurationEx</b> failed due to insufficient resources.</p><dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl><p><b>NdisOpenConfigurationEx</b> returns NDIS_STATUS_FAILURE if none of the preceding values
       applies.</p>

<p> </p>

## -remarks
<p><b>NdisOpenConfigurationEx</b> returns a configuration handle at the 
    <i>ConfigurationHandle</i> parameter. The configuration handle is associated with a registry key that
    identifies the location of the configuration parameters. The caller can pass the configuration handle to
    other NDIS configuration functions to read or write information in the registry.</p>

<p>To access the configuration information, use the configuration handle with the following
    functions:</p>

<p>
<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>
</p>

<p>
<a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a>
</p>

<p>
<a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyname.md">
       NdisOpenConfigurationKeyByName</a>
</p>

<p>
<a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyindex.md">
       NdisOpenConfigurationKeyByIndex</a>
</p>

<p>The type of registry data that is associated with the configuration handle depends on the type of
    handle that the caller passes to 
    <b>NdisOpenConfigurationEx</b> in the 
    <b>NdisHandle</b> member of the 
    <a href="..\ndis\ns-ndis--ndis-configuration-object.md">
    NDIS_CONFIGURATION_OBJECT</a> structure that is referenced by the 
    <i>ConfigObject</i> parameter. The handle can identify parameters that are associated with the driver or
    with an instance of the driver.</p>

<p>If the driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the miniport driver's
    configuration parameters are stored. The miniport driver can use the configuration handle until it calls
    the 
    <a href="..\ndis\nf-ndis-ndismderegisterminiportdriver.md">
    NdisMDeregisterMiniportDriver</a> function.</p>

<p>If the driver obtained the handle in 
    <b>NdisHandle</b> from the 
    <i>MiniportAdapterHandle</i> parameter of the 
    <a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where a miniport adapter's
    configuration parameters are stored. A miniport driver can pass the configuration handle to the 
    <a href="..\ndis\nf-ndis-ndisreadnetworkaddress.md">NdisReadNetworkAddress</a> function to
    retrieve network address information that can be configured by software and administered locally.
    Miniport drivers can use the configuration handle until NDIS halts the miniport adapter and the 
    <a href="..\ndis\nc-ndis-miniport-halt.md">MiniportHaltEx</a> function returns.</p>

<p>If the driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">
    NdisRegisterProtocolDriver</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the protocol driver's
    configuration parameters are stored. The protocol driver can use the configuration handle until it calls
    the 
    <a href="..\ndis\nf-ndis-ndisderegisterprotocoldriver.md">
    NdisDeregisterProtocolDriver</a> function.</p>

<p>If the handle in 
    <b>NdisHandle</b> is a pointer to an 
    <a href="..\ndis\ns-ndis--ndis-bind-parameters.md">NDIS_BIND_PARAMETERS</a> structure that
    NDIS passed at the 
    <i>BindParameters</i> parameter of the 
    <a href="..\ndis\nc-ndis-protocol-bind-adapter-ex.md">ProtocolBindAdapterEx</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where configuration parameters
    for a protocol binding are stored. Protocol drivers can use the configuration handle until the bind
    operation is complete.</p>

<p>If the driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the configuration
    parameters for a protocol binding are stored. The protocol driver can use the configuration handle until
    it calls the 
    <a href="..\ndis\nf-ndis-ndiscloseadapterex.md">NdisCloseAdapterEx</a> function.</p>

<p>If a filter driver obtained the handle in 
    <b>NdisHandle</b> by calling the 
    <a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where the filter driver's
    configuration parameters are stored. Filter drivers can use the configuration handle until they call the 
    <a href="..\ndis\nf-ndis-ndisfderegisterfilterdriver.md">
    NdisFDeregisterFilterDriver</a> function.</p>

<p>If a filter driver obtained the handle in 
    <b>NdisHandle</b> from the 
    <i>NdisFilterHandle</i> parameter of the 
    <a href="..\ndis\nc-ndis-filter-attach.md">FilterAttach</a> function, 
    <b>NdisOpenConfigurationEx</b> provides a handle to the registry location where a filter modules
    configuration parameters are stored. The filter driver can use the configuration handle until NDIS
    detaches the filter module and the 
    <a href="..\ndis\nc-ndis-filter-detach.md">FilterDetach</a> function returns. If a
    monitoring filter driver specifies the NDIS_CONFIG_FLAG_FILTER_INSTANCE_CONFIGURATION flag in the 
    <b>Flags</b> member of the 
    <a href="..\ndis\ns-ndis--ndis-configuration-object.md">
    NDIS_CONFIGURATION_OBJECT</a> structure, the driver can access the filter module configuration for a
    specific filter module when there are multiple filter modules configured over the same miniport adapter.
    Modifying filter drivers must not use this flag.</p>

<p>After a driver is done accessing the configuration information, the driver must call the 
    <a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a> function to
    release the configuration handle and related resources.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>, <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter-attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter-detach.md">FilterDetach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-bind-parameters.md">NDIS_BIND_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-configuration-object.md">NDIS_CONFIGURATION_OBJECT</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscloseadapterex.md">NdisCloseAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisderegisterprotocoldriver.md">NdisDeregisterProtocolDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfderegisterfilterdriver.md">NdisFDeregisterFilterDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismderegisterminiportdriver.md">
   NdisMDeregisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyindex.md">
   NdisOpenConfigurationKeyByIndex</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyname.md">
   NdisOpenConfigurationKeyByName</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreadnetworkaddress.md">NdisReadNetworkAddress</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-bind-adapter-ex.md">ProtocolBindAdapterEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisOpenConfigurationEx function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
