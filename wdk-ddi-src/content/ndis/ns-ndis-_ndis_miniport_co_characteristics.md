---
UID: NS:ndis._NDIS_MINIPORT_CO_CHARACTERISTICS
title: _NDIS_MINIPORT_CO_CHARACTERISTICS
author: windows-driver-content
description: The NDIS_MINIPORT_CO_CHARACTERISTICS structure specifies the CoNDIS entry points for a CoNDIS miniport driver.
old-location: netvista\ndis_miniport_co_characteristics.htm
old-project: netvista
ms.assetid: 9348c338-9fb4-4eee-a50f-f709748da56b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_MINIPORT_CO_CHARACTERISTICS, NDIS_MINIPORT_CO_CHARACTERISTICS, *PNDIS_MINIPORT_CO_CHARACTERISTICS
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
req.alt-api: NDIS_MINIPORT_CO_CHARACTERISTICS
req.alt-loc: ndis.h
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
req.typenames: NDIS_MINIPORT_CO_CHARACTERISTICS, *PNDIS_MINIPORT_CO_CHARACTERISTICS
---

# _NDIS_MINIPORT_CO_CHARACTERISTICS structure



## -description
The NDIS_MINIPORT_CO_CHARACTERISTICS structure specifies the CoNDIS entry points for a CoNDIS
  miniport driver.



## -syntax

````
typedef struct _NDIS_MINIPORT_CO_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                 Header;
  ULONG                              Flags;
  W_CO_CREATE_VC_HANDLER             CoCreateVcHandler;
  W_CO_DELETE_VC_HANDLER             CoDeleteVcHandler;
  W_CO_ACTIVATE_VC_HANDLER           CoActivateVcHandler;
  W_CO_DEACTIVATE_VC_HANDLER         CoDeactivateVcHandler;
  W_CO_SEND_NET_BUFFER_LISTS_HANDLER CoSendNetBufferListsHandler;
  W_CO_OID_REQUEST_HANDLER           CoOidRequestHandler;
} NDIS_MINIPORT_CO_CHARACTERISTICS, *PNDIS_MINIPORT_CO_CHARACTERISTICS;
````


## -struct-fields

### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     miniport driver CoNDIS characteristics structure (NDIS_MINIPORT_CO_CHARACTERISTICS). The driver sets the
     
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CO_MINIPORT_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_MINIPORT_CO_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_CO_CHARACTERISTICS_REVISION_1.


### -field Flags

Reserved for NDIS.


### -field CoCreateVcHandler

The entry point of the driver's 
     <a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a> function. If
     this entry point is for an integrated miniport call manager (MCM) driver, this member should be <b>NULL</b>,
     because NDIS calls such a driver's 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function
     instead. For more information about 
     <i>ProtocolCoCreateVc</i> in an MCM, see 
     <a href="..\ndis\ns-ndis-_ndis_co_call_manager_optional_handlers.md">
     NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>.


### -field CoDeleteVcHandler

The entry point of the driver's 
     <a href="..\ndis\nc-ndis-miniport_co_delete_vc.md">MiniportCoDeleteVc</a> function. If
     this entry point is for an integrated miniport call manager (MCM) driver, this member should be <b>NULL</b>,
     because NDIS calls such a driver's 
     <a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a> function
     instead. For more information about 
     <i>ProtocolCoDeleteVc</i> in an MCM, see 
     <a href="..\ndis\ns-ndis-_ndis_co_call_manager_optional_handlers.md">
     NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>.


### -field CoActivateVcHandler

The entry point of the driver's 
     <a href="..\ndis\nc-ndis-miniport_co_activate_vc.md">
     MiniportCoActivateVc</a> function.


### -field CoDeactivateVcHandler

The entry point of the driver's 
     <a href="..\ndis\nc-ndis-miniport_co_deactivate_vc.md">
     MiniportCoDeactivateVc</a> function.


### -field CoSendNetBufferListsHandler

The entry point of the driver's 
     <a href="..\ndis\nc-ndis-miniport_co_send_net_buffer_lists.md">
     MiniportCoSendNetBufferLists</a> function.


### -field CoOidRequestHandler

The entry point of the driver's 
     <a href="..\ndis\nc-ndis-miniport_co_oid_request.md">
     MiniportCoOidRequest</a> function.


## -remarks
To specify entry points for CoNDIS, a miniport driver initializes an NDIS_MINIPORT_CO_CHARACTERISTICS
    structure and passes it to the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">
    NdisSetOptionalHandlers</a> function.

The miniport driver calls 
    <b>NdisSetOptionalHandlers</b> from the 
    <a href="netvista.miniportsetoptions">MiniportSetOptions</a> function.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_activate_vc.md">MiniportCoActivateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_deactivate_vc.md">MiniportCoDeactivateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_delete_vc.md">MiniportCoDeleteVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_oid_request.md">MiniportCoOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_send_net_buffer_lists.md">
   MiniportCoSendNetBufferLists</a>
</dt>
<dt>
<a href="netvista.miniportsetoptions">MiniportSetOptions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_co_call_manager_optional_handlers.md">
   NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_CO_CHARACTERISTICS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

