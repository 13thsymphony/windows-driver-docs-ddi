---
UID: NS:dot11wdi._WDI_TX_COMPLETE_DATA
title: "_WDI_TX_COMPLETE_DATA"
author: windows-driver-content
description: The WDI_TX_COMPLETE_DATA structure defines TX completion data.
old-location: netvista\wdi_tx_complete_data.htm
old-project: netvista
ms.assetid: bf7951de-3368-4faf-9bae-272c6d76d1a0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDI_TX_COMPLETE_DATA, PWDI_TX_COMPLETE_DATA, PWDI_TX_COMPLETE_DATA structure pointer [Network Drivers Starting with Windows Vista], WDI_TX_COMPLETE_DATA, WDI_TX_COMPLETE_DATA structure [Network Drivers Starting with Windows Vista], _WDI_TX_COMPLETE_DATA, dot11wdi/PWDI_TX_COMPLETE_DATA, dot11wdi/WDI_TX_COMPLETE_DATA, netvista.wdi_tx_complete_data, netvista.wifi_tx_complete_data"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dot11wdi.h
api_name:
-	WDI_TX_COMPLETE_DATA
product: Windows
targetos: Windows
req.typenames: WDI_TX_COMPLETE_DATA, *PWDI_TX_COMPLETE_DATA
---

# _WDI_TX_COMPLETE_DATA structure
The WDI_TX_COMPLETE_DATA structure defines TX completion data.

## Syntax
````
typedef struct _WDI_TX_COMPLETE_DATA {
  UINT16           SeqCtl;
  UINT8            PnLength;
  UINT8            RetryCount;
  UINT16           wPad;
  WDI_TXRX_MPDU_PN MpduPN;
  UINT64           ReplayIHVReserved0;
  UINT64           ReplayIHVReserved1;
} WDI_TX_COMPLETE_DATA, *PWDI_TX_COMPLETE_DATA;
````

## Members


`MpduPN`

The MPDU PN.

`PnLength`

The MPDU PN length for the transmitted frame.

`ReplayIHVReserved0`

Reserved for IHV use.

`ReplayIHVReserved1`

Reserved for IHV use.

`RetryCount`

The number of attempts to transmit the frame.

`SeqCtl`

The value of the sequence control field from the frame transmission.

`wPad`

This member is reserved.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |