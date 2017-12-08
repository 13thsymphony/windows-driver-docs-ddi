---
UID: NS.UCXROOTHUB._UCX_ROOTHUB_CONFIG
title: _UCX_ROOTHUB_CONFIG
author: windows-driver-content
description: Contains pointers to event callback functions for creating the root hub by calling UcxRootHubCreate. Initialize this structure by calling UCX_ROOTHUB_CONFIG_INIT initialization function (see Ucxclass.h).
old-location: buses\_ucx_roothub_config.htm
old-project: usbref
ms.assetid: 27E54F0D-2163-4D7C-B204-336EE0227488
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UCX_ROOTHUB_CONFIG, *PUCX_ROOTHUB_CONFIG, UCX_ROOTHUB_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCX_ROOTHUB_CONFIG
req.alt-loc: ucxroothub.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# _UCX_ROOTHUB_CONFIG structure



## -description
Contains pointers to event callback functions for creating the root hub by calling <a href="buses._ucxroothubcreate">UcxRootHubCreate</a>. Initialize this structure by calling <b>UCX_ROOTHUB_CONFIG_INIT</b> initialization function (see Ucxclass.h).


## -syntax

````
typedef struct _UCX_ROOTHUB_CONFIG {
  ULONG                            Size;
  ULONG                            NumberOfPresentedControlUrbCallbacks;
  PEVT_UCX_ROOTHUB_CONTROL_URB     EvtRootHubClearHubFeature;
  PEVT_UCX_ROOTHUB_CONTROL_URB     EvtRootHubClearPortFeature;
  PEVT_UCX_ROOTHUB_CONTROL_URB     EvtRootHubGetHubStatus;
  PEVT_UCX_ROOTHUB_CONTROL_URB     EvtRootHubGetPortStatus;
  PEVT_UCX_ROOTHUB_CONTROL_URB     EvtRootHubSetHubFeature;
  PEVT_UCX_ROOTHUB_CONTROL_URB     EvtRootHubSetPortFeature;
  PEVT_UCX_ROOTHUB_CONTROL_URB     EvtRootHubGetPortErrorCount;
  PEVT_UCX_ROOTHUB_CONTROL_URB     EvtRootHubControlUrb;
  PEVT_UCX_ROOTHUB_INTERRUPT_TX    EvtRootHubInterruptTx;
  PEVT_UCX_ROOTHUB_GET_INFO        EvtRootHubGetInfo;
  PEVT_UCX_ROOTHUB_GET_20PORT_INFO EvtRootHubGet20PortInfo;
  PEVT_UCX_ROOTHUB_GET_30PORT_INFO EvtRootHubGet30PortInfo;
  WDF_OBJECT_ATTRIBUTES            WdfRequestAttributes;
} UCX_ROOTHUB_CONFIG, *P_UCX_ROOTHUB_CONFIG;
````


## -struct-fields

### -field Size

The size in bytes of this structure.

### -field NumberOfPresentedControlUrbCallbacks

The number of control requests sent to the default endpoint.

### -field EvtRootHubClearHubFeature

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_control_urb.md">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.

### -field EvtRootHubClearPortFeature

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_control_urb.md">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.

### -field EvtRootHubGetHubStatus

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_control_urb.md">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.

### -field EvtRootHubGetPortStatus

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_control_urb.md">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.

### -field EvtRootHubSetHubFeature

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_control_urb.md">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.

### -field EvtRootHubSetPortFeature

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_control_urb.md">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.

### -field EvtRootHubGetPortErrorCount

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_control_urb.md">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.

### -field EvtRootHubControlUrb

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_control_urb.md">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.

### -field EvtRootHubInterruptTx

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_interrupt_tx.md">EVT_UCX_ROOTHUB_INTERRUPT_TX</a> callback function.

### -field EvtRootHubGetInfo

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_get_info.md">EVT_UCX_ROOTHUB_GET_INFO</a> callback function.

### -field EvtRootHubGet20PortInfo

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_get_20port_info.md">EVT_UCX_ROOTHUB_GET_20PORT_INFO</a> callback function.

### -field EvtRootHubGet30PortInfo

A pointer to the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_get_30port_info.md">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a> callback function.

### -field WdfRequestAttributes

A pointer to a <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies initialization parameters.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ucxroothub.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
</table>