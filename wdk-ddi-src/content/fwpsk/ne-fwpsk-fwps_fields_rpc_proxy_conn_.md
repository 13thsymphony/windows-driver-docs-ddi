---
UID: NE.fwpsk.FWPS_FIELDS_RPC_PROXY_CONN_
title: FWPS_FIELDS_RPC_PROXY_CONN_
author: windows-driver-content
description: The FWPS_FIELDS_RPC_PROXY_CONN enumeration type specifies the data field identifiers for the FWPS_LAYER_RPC_PROXY_CONN run-time filtering layer.
old-location: netvista\fwps_fields_rpc_proxy_conn.htm
old-project: NetVista
ms.assetid: 22d60d8c-dad0-4b2c-9ae7-0e30552f5a81
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FWPS_FIELDS_RPC_PROXY_CONN_, FWPS_FIELDS_RPC_PROXY_CONN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_RPC_PROXY_CONN
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# FWPS_FIELDS_RPC_PROXY_CONN_ enumeration



## -description
The FWPS_FIELDS_RPC_PROXY_CONN enumeration type specifies the data field identifiers for the
  FWPS_LAYER_RPC_PROXY_CONN 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layer</a>.



## -syntax

````
typedef enum FWPS_FIELDS_RPC_PROXY_CONN_ { 
  FWPS_FIELD_RPC_PROXY_CONN_CLIENT_TOKEN,
  FWPS_FIELD_RPC_PROXY_CONN_SERVER_NAME,
  FWPS_FIELD_RPC_PROXY_CONN_SERVER_PORT,
  FWPS_FIELD_RPC_PROXY_CONN_PROXY_AUTH_TYPE,
  FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_KEY_LENGTH,
  FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_OID,
  FWPS_FIELD_RPC_PROXY_CONN_MAX
} FWPS_FIELDS_RPC_PROXY_CONN;
````


## -enum-fields

### -field FWPS_FIELD_RPC_PROXY_CONN_CLIENT_TOKEN

The identification of the client when using RpcProxy.


### -field FWPS_FIELD_RPC_PROXY_CONN_SERVER_NAME

The name of the RPC server when using RpcProxy.


### -field FWPS_FIELD_RPC_PROXY_CONN_SERVER_PORT

The port on the RPC server when using RpcProxy.


### -field FWPS_FIELD_RPC_PROXY_CONN_PROXY_AUTH_TYPE

The RPC proxy authentication service type. For more information about authentication service
     types, see Authentication-Service Constants in the RPC section of the Windows SDK.


### -field FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_KEY_LENGTH

The secure socket layer (SSL) key length in the client certificate.


### -field FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_OID

The object identifier (OID) in the client certificate.


### -field FWPS_FIELD_RPC_PROXY_CONN_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
</table>