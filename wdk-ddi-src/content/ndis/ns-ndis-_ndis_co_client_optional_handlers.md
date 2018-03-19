---
UID: NS:ndis._NDIS_CO_CLIENT_OPTIONAL_HANDLERS
title: "_NDIS_CO_CLIENT_OPTIONAL_HANDLERS"
author: windows-driver-content
description: The NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure specifies entry points for CoNDIS client ProtocolXxx functions for the protocol driver that passes this structure to the NdisSetOptionalHandlers function.
old-location: netvista\ndis_co_client_optional_handlers.htm
old-project: netvista
ms.assetid: 1f2285bb-be70-4496-905d-89106bf3712a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_CO_CLIENT_OPTIONAL_HANDLERS, NDIS_CO_CLIENT_OPTIONAL_HANDLERS, NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_CO_CLIENT_OPTIONAL_HANDLERS, PNDIS_CO_CLIENT_OPTIONAL_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CO_CLIENT_OPTIONAL_HANDLERS, condis_structures_ref_63c453a1-6ad8-4d31-93ff-340dba8433db.xml, ndis/NDIS_CO_CLIENT_OPTIONAL_HANDLERS, ndis/PNDIS_CO_CLIENT_OPTIONAL_HANDLERS, netvista.ndis_co_client_optional_handlers"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_CO_CLIENT_OPTIONAL_HANDLERS
product: Windows
targetos: Windows
req.typenames: NDIS_CO_CLIENT_OPTIONAL_HANDLERS, *PNDIS_CO_CLIENT_OPTIONAL_HANDLERS
---

# _NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure
The NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure specifies entry points for CoNDIS client 
  <i>ProtocolXxx</i> functions for the protocol driver that passes this structure to the 
  <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">
  NdisSetOptionalHandlers</a> function.

## Syntax
````
typedef struct _NDIS_CO_CLIENT_OPTIONAL_HANDLERS {
  NDIS_OBJECT_HEADER                  Header;
  ULONG                               Reserved;
  CO_CREATE_VC_HANDLER                ClCreateVcHandler;
  CO_DELETE_VC_HANDLER                ClDeleteVcHandler;
  CO_OID_REQUEST_HANDLER              ClOidRequestHandler;
  CO_OID_REQUEST_COMPLETE_HANDLER     ClOidRequestCompleteHandler;
  CL_OPEN_AF_COMPLETE_HANDLER_EX      ClOpenAfCompleteHandlerEx;
  CL_CLOSE_AF_COMPLETE_HANDLER        ClCloseAfCompleteHandler;
  CL_REG_SAP_COMPLETE_HANDLER         ClRegisterSapCompleteHandler;
  CL_DEREG_SAP_COMPLETE_HANDLER       ClDeregisterSapCompleteHandler;
  CL_MAKE_CALL_COMPLETE_HANDLER       ClMakeCallCompleteHandler;
  CL_MODIFY_CALL_QOS_COMPLETE_HANDLER ClModifyCallQoSCompleteHandler;
  CL_CLOSE_CALL_COMPLETE_HANDLER      ClCloseCallCompleteHandler;
  CL_ADD_PARTY_COMPLETE_HANDLER       ClAddPartyCompleteHandler;
  CL_DROP_PARTY_COMPLETE_HANDLER      ClDropPartyCompleteHandler;
  CL_INCOMING_CALL_HANDLER            ClIncomingCallHandler;
  CL_INCOMING_CALL_QOS_CHANGE_HANDLER ClIncomingCallQoSChangeHandler;
  CL_INCOMING_CLOSE_CALL_HANDLER      ClIncomingCloseCallHandler;
  CL_INCOMING_DROP_PARTY_HANDLER      ClIncomingDropPartyHandler;
  CL_CALL_CONNECTED_HANDLER           ClCallConnectedHandler;
  CL_NOTIFY_CLOSE_AF_HANDLER          ClNotifyCloseAfHandler;
} NDIS_CO_CLIENT_OPTIONAL_HANDLERS, *PNDIS_CO_CLIENT_OPTIONAL_HANDLERS;
````

## Members


`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     protocol driver CoNDIS characteristics structure (NDIS_CO_CLIENT_OPTIONAL_HANDLERS). The driver sets the
     
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CO_CLIENT_OPTIONAL_HANDLERS, the 
     <b>Revision</b> member to NDIS_CO_CLIENT_OPTIONAL_HANDLERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_CO_CLIENT_OPTIONAL_HANDLERS_REVISION_1.

`Reserved`

Reserved for NDIS.

`ClCreateVcHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.

`ClDeleteVcHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a> function.

`ClOidRequestHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_co_oid_request.md">
     ProtocolCoOidRequest</a> function.

`ClOidRequestCompleteHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
     ProtocolCoOidRequestComplete</a> function.

`ClOpenAfCompleteHandlerEx`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_open_af_complete_ex.md">
     ProtocolClOpenAfCompleteEx</a> function.

`ClCloseAfCompleteHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">
     ProtocolClCloseAfComplete</a> function.

`ClRegisterSapCompleteHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_register_sap_complete.md">
     ProtocolClRegisterSapComplete</a> function. A client uses this function to accept incoming calls from
     remote machines.

`ClDeregisterSapCompleteHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_deregister_sap_complete.md">
     ProtocolClDeregisterSapComplete</a> function.

`ClMakeCallCompleteHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_make_call_complete.md">
     ProtocolClMakeCallComplete</a> function. A client uses this function to make outgoing calls to remote
     machines.

`ClModifyCallQoSCompleteHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_modify_call_qos_complete.md">
     ProtocolClModifyCallQoSComplete</a> function. A client uses this function to dynamically make changes
     in the quality of service (QoS) on an established virtual connection (VC) or to negotiate with the call
     manager to establish the QoS when the client sets up an incoming call.

`ClCloseCallCompleteHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_close_call_complete.md">
     ProtocolClCloseCallComplete</a> function.

`ClAddPartyCompleteHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_add_party_complete.md">
     ProtocolClAddPartyComplete</a> function. A client uses this function to establish point-to-multipoint
     VCs for outgoing calls to remote machines.

`ClDropPartyCompleteHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_drop_party_complete.md">
     ProtocolClDropPartyComplete</a> function.

`ClIncomingCallHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">
     ProtocolClIncomingCall</a> function. A client uses this function to accept incoming calls from remote
     machines.

`ClIncomingCallQoSChangeHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_incoming_call_qos_change.md">
     ProtocolClIncomingCallQoSChange</a> function. A client uses this function to accept incoming calls
     from remote machines on which the sending client can dynamically change the QoS.

`ClIncomingCloseCallHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_incoming_close_call.md">
     ProtocolClIncomingCloseCall</a> function.

`ClIncomingDropPartyHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_incoming_drop_party.md">
     ProtocolClIncomingDropParty</a> function.

`ClCallConnectedHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_call_connected.md">
     ProtocolClCallConnected</a> function. A client uses this function to accept incoming calls from remote
     machines.

`ClNotifyCloseAfHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cl_notify_close_af.md">
     ProtocolClNotifyCloseAf</a> function.

## Remarks
To specify entry points as a CoNDIS client, a protocol driver initializes an
    NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure and passes it to the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">
    NdisSetOptionalHandlers</a> function.

The client calls 
    <b>NdisSetOptionalHandlers</b> from the 
    <a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a> function. The
    client must set every 
    <b>Cl</b><i>Xxx</i> member in the NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure to a caller-supplied 
    <i>ProtocolXxx</i> function, even if the call manager does not support incoming calls, outgoing calls, or
    point-to-multipoint connections. For whatever subset of connection-oriented functionality that a client
    does not support, its placeholder 
    <i>ProtocolXxx</i> functions should return NDIS_STATUS_NOT_SUPPORTED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="..\ndis\nc-ndis-protocol_cl_close_call_complete.md">ProtocolClCloseCallComplete</a>



<a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a>



<a href="..\ndis\nc-ndis-protocol_cl_modify_call_qos_complete.md">
   ProtocolClModifyCallQoSComplete</a>



<a href="..\ndis\nc-ndis-protocol_co_oid_request.md">ProtocolCoOidRequest</a>



<a href="..\ndis\nc-ndis-protocol_cl_add_party_complete.md">ProtocolClAddPartyComplete</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_drop_party.md">ProtocolClIncomingDropParty</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a>



<a href="..\ndis\nc-ndis-protocol_cl_make_call_complete.md">ProtocolClMakeCallComplete</a>



<a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">ProtocolClCloseAfComplete</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
   ProtocolCoOidRequestComplete</a>



<a href="..\ndis\nc-ndis-protocol_cl_deregister_sap_complete.md">
   ProtocolClDeregisterSapComplete</a>



<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>



<a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">ProtocolCoAfRegisterNotify</a>



<a href="..\ndis\nc-ndis-protocol_cl_open_af_complete_ex.md">ProtocolClOpenAfCompleteEx</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_close_call.md">ProtocolClIncomingCloseCall</a>



<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="..\ndis\nc-ndis-protocol_cl_register_sap_complete.md">
   ProtocolClRegisterSapComplete</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_call_qos_change.md">
   ProtocolClIncomingCallQoSChange</a>



<a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a>



<a href="..\ndis\nc-ndis-protocol_cl_call_connected.md">ProtocolClCallConnected</a>



<a href="..\ndis\nc-ndis-protocol_cl_drop_party_complete.md">ProtocolClDropPartyComplete</a>