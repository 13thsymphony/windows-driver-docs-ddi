---
UID: NS:dot11wdi._WDI_TXRX_TARGET_CAPABILITIES
title: "_WDI_TXRX_TARGET_CAPABILITIES"
author: windows-driver-content
description: The WDI_TXRX_CAPABILITIES structure defines the target capabilities.
old-location: netvista\wdi_txrx_capabilities.htm
old-project: netvista
ms.assetid: 7a1d3ffd-6f5e-429d-8c2f-a141f98ccad8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: dot11wdi/PWDI_TXRX_CAPABILITIES, _WDI_TXRX_TARGET_CAPABILITIES, WDI_TXRX_CAPABILITIES, *PWDI_TXRX_CAPABILITIES, WDI_TXRX_CAPABILITIES structure [Network Drivers Starting with Windows Vista], PWDI_TXRX_CAPABILITIES structure pointer [Network Drivers Starting with Windows Vista], netvista.wdi_txrx_capabilities, PWDI_TXRX_CAPABILITIES, dot11wdi/WDI_TXRX_TARGET_CAPABILITIES, netvista.wdi_txrx_target_capabilities, netvista.wifi_txrx_target_capabilities
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dot11wdi.h
apiname:
-	WDI_TXRX_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: WDI_TXRX_CAPABILITIES, *PWDI_TXRX_CAPABILITIES
---

# _WDI_TXRX_TARGET_CAPABILITIES structure
The 
   WDI_TXRX_CAPABILITIES structure defines the target capabilities.

## Syntax
````
typedef struct _WDI_TXRX_CAPABILITIES {
  WDI_INTERCONNECT_TYPE InterconnectType;
  struct {
    BOOLEAN TargetPriorityQueueing;
    UINT16  MaxMemBlocksPerFrame;
    BOOLEAN ExplicitSendCompleteFlagRequired;
    UINT8   bPad;
    UINT16  MinEffectiveSize;
    UINT16  FrameSizeGranularity;
  } TransmitCapabilities;
  struct {
    BOOLEAN RxTxForwarding;
    UINT32  MaxThroughput;
  } ReceiveCapabilities;
} WDI_TXRX_CAPABILITIES, *PWDI_TXRX_CAPABILITIES;
````

## Members


`InterconnectType`

Interconnect type of the target.

`ReceiveCapabilities`

Receive capabilities.

`TransmitCapabilities`

Transmit capabilities.



#### MaxMemBlocksPerFrame

Maximum number of Scatter Gather elements in a frame.  WDI coalesces frames as necessary so that the IHV miniport does not receive a frame that requires more scatter gather elements than specified by this capability.  For best performance, it is suggested that this capability is set higher than the typical frame as the coalescing requires a memory copy.  If this capability is not greater than the maximum frame size divided by page size, WDI may be unable to successfully coalesce the frame and it may be dropped.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |