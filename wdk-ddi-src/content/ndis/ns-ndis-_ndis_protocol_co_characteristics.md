---
UID : NS:ndis._NDIS_PROTOCOL_CO_CHARACTERISTICS
title : _NDIS_PROTOCOL_CO_CHARACTERISTICS
author : windows-driver-content
description : The NDIS_PROTOCOL_CO_CHARACTERISTICS structure specifies CoNDIS entry points for CoNDIS protocol drivers.
old-location : netvista\ndis_protocol_co_characteristics.htm
old-project : netvista
ms.assetid : 855e3231-502c-4c6f-99f9-7ad85354ccd5
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : _NDIS_PROTOCOL_CO_CHARACTERISTICS, netvista.ndis_protocol_co_characteristics, NDIS_PROTOCOL_CO_CHARACTERISTICS, ndis/NDIS_PROTOCOL_CO_CHARACTERISTICS, PNDIS_PROTOCOL_CO_CHARACTERISTICS, condis_structures_ref_a4228b74-0f76-4800-ad95-e7ef3d92df42.xml, *PNDIS_PROTOCOL_CO_CHARACTERISTICS, PNDIS_PROTOCOL_CO_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], NDIS_PROTOCOL_CO_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], ndis/PNDIS_PROTOCOL_CO_CHARACTERISTICS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_PROTOCOL_CO_CHARACTERISTICS, NDIS_PROTOCOL_CO_CHARACTERISTICS"
---

# _NDIS_PROTOCOL_CO_CHARACTERISTICS structure
The NDIS_PROTOCOL_CO_CHARACTERISTICS structure specifies CoNDIS entry points for CoNDIS protocol
  drivers.

## Syntax
````
typedef struct _NDIS_PROTOCOL_CO_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                        Header;
  ULONG                                     Flags;
  CO_STATUS_HANDLER_EX                      CoStatusHandlerEx;
  CO_AF_REGISTER_NOTIFY_HANDLER             CoAfRegisterNotifyHandler;
  CO_RECEIVE_NET_BUFFER_LISTS_HANDLER       CoReceiveNetBufferListsHandler;
  CO_SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER CoSendNetBufferListsCompleteHandler;
} NDIS_PROTOCOL_CO_CHARACTERISTICS, *PNDIS_PROTOCOL_CO_CHARACTERISTICS;
````

## Members


`CoAfRegisterNotifyHandler`

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocolcoafregisternotify" tabindex="0"><i>
     ProtocolCoAfRegisterNotify</i></mshelp:link> function.

`CoReceiveNetBufferListsHandler`

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocolcoreceivenetbufferlists" tabindex="0"><i>
     ProtocolCoReceiveNetBufferLists</i></mshelp:link> function.

`CoSendNetBufferListsCompleteHandler`

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocolcosendnetbufferlistscomplete" tabindex="0"><i>
     ProtocolCoSendNetBufferListsComplete</i></mshelp:link> function.

`CoStatusHandlerEx`

The entry point of the driver's 
     <a href="..\ndis\nc-ndis-protocol_co_status_ex.md">ProtocolCoStatusEx</a> function.

`Flags`

Reserved for NDIS.

`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     protocol driver CoNDIS characteristics structure (NDIS_PROTOCOL_CO_CHARACTERISTICS). The driver sets the
     
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CO_PROTOCOL_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_PROTOCOL_CO_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PROTOCOL_CO_CHARACTERISTICS_REVISION_1.

## Remarks
To specify entry points for CoNDIS, a protocol driver initializes an NDIS_PROTOCOL_CO_CHARACTERISTICS
    structure and passes it to the 
    <mshelp:link keywords="netvista.ndissetoptionalhandlers" tabindex="0"><b>
    NdisSetOptionalHandlers</b></mshelp:link> function.

The protocol driver calls 
    <b>NdisSetOptionalHandlers</b> from the 
    <a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<mshelp:link keywords="netvista.protocolcoreceivenetbufferlists" tabindex="0"><i>
   ProtocolCoReceiveNetBufferLists</i></mshelp:link>

<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>

<a href="..\ndis\nc-ndis-protocol_co_status_ex.md">ProtocolCoStatusEx</a>

<a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a>

<mshelp:link keywords="netvista.protocolcosendnetbufferlistscomplete" tabindex="0"><i>
   ProtocolCoSendNetBufferListsComplete</i></mshelp:link>

<a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">ProtocolCoAfRegisterNotify</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROTOCOL_CO_CHARACTERISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>