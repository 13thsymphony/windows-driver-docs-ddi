---
UID : NS:dot11wdi._WDI_RX_METADATA
title : "_WDI_RX_METADATA"
author : windows-driver-content
description : The WDI_RX_METADATA structure defines the RX metadata.
old-location : netvista\wdi_rx_metadata.htm
old-project : netvista
ms.assetid : da1ac5d6-fb17-4034-8448-d582bafda870
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.wifi_rx_metadata, WDI_RX_METADATA, dot11wdi/WDI_RX_METADATA, *PWDI_RX_METADATA, _WDI_RX_METADATA, dot11wdi/PWDI_RX_METADATA, netvista.wdi_rx_metadata, WDI_RX_METADATA structure [Network Drivers Starting with Windows Vista], PWDI_RX_METADATA, PWDI_RX_METADATA structure pointer [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dot11wdi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDI_RX_METADATA, WDI_RX_METADATA"
---

# _WDI_RX_METADATA structure
The 
  WDI_RX_METADATA structure defines the RX metadata.

The RX Engine specifies this metadata in the <b>rxMetadata</b> section of the <a href="..\dot11wdi\ns-dot11wdi-_wdi_frame_metadata.md">WDI_FRAME_METADATA</a> buffer attached to each <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> (in MiniportReserved[0]). Each NET_BUFFER_LIST represents an MPDU.  The IHV miniport driver must not allocate a <a href="..\windot11\ns-windot11-dot11_extsta_recv_context.md">DOT11_EXTSTA_RECV_CONTEXT</a> structure as this is handled by WDI.

## Syntax
````
typedef struct _WDI_RX_METADATA {
  WDI_FRAME_PAYLOAD_TYPE PayloadType;
} WDI_RX_METADATA, *PWDI_RX_METADATA;
````

## Members


`PayloadType`

The payload type, specified for each MPDU.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |

## See Also

<a href="..\dot11wdi\ns-dot11wdi-_wdi_frame_metadata.md">WDI_FRAME_METADATA</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WDI_RX_METADATA structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>