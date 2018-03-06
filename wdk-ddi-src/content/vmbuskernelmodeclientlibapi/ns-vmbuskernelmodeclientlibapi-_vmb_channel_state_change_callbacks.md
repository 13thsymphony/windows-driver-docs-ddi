---
UID: NS:vmbuskernelmodeclientlibapi._VMB_CHANNEL_STATE_CHANGE_CALLBACKS
title: "_VMB_CHANNEL_STATE_CHANGE_CALLBACKS"
author: windows-driver-content
description: The VMB_CHANNEL_STATE_CHANGE_CALLBACKS structure contains callback functions that relate to the state changes for a channel.
old-location: netvista\vmb_channel_state_change_callbacks.htm
old-project: netvista
ms.assetid: 01A9A947-76F0-407C-8480-B2721A9A8A7B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVMB_CHANNEL_STATE_CHANGE_CALLBACKS, PVMB_CHANNEL_STATE_CHANGE_CALLBACKS, PVMB_CHANNEL_STATE_CHANGE_CALLBACKS structure pointer [Network Drivers Starting with Windows Vista], VMB_CHANNEL_STATE_CHANGE_CALLBACKS, VMB_CHANNEL_STATE_CHANGE_CALLBACKS structure [Network Drivers Starting with Windows Vista], _VMB_CHANNEL_STATE_CHANGE_CALLBACKS, netvista.vmb_channel_state_change_callbacks, vmbuskernelmodeclientlibapi/PVMB_CHANNEL_STATE_CHANGE_CALLBACKS, vmbuskernelmodeclientlibapi/VMB_CHANNEL_STATE_CHANGE_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	VmbusKernelModeClientLibApi.h
api_name:
-	VMB_CHANNEL_STATE_CHANGE_CALLBACKS
product: Windows
targetos: Windows
req.typenames: VMB_CHANNEL_STATE_CHANGE_CALLBACKS, *PVMB_CHANNEL_STATE_CHANGE_CALLBACKS
req.product: Windows 10 or later.
---

# _VMB_CHANNEL_STATE_CHANGE_CALLBACKS structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VMB_CHANNEL_STATE_CHANGE_CALLBACKS</b> structure contains callback functions that relate to the state changes for a channel.

## Syntax
````
typedef struct _VMB_CHANNEL_STATE_CHANGE_CALLBACKS {
  ULONG                        Version;
  ULONG                        Size;
  PFN_VMB_CHANNEL_OPENED       EvtChannelOpened;
  PFN_VMB_CHANNEL_CLOSED       EvtChannelClosed;
  PFN_VMB_CHANNEL_SUSPEND      EvtChannelSuspend;
  PFN_VMB_CHANNEL_STARTED      EvtChannelStarted;
  PFN_VMB_CHANNEL_POST_STARTED EvtChannelPostStarted;
} VMB_CHANNEL_STATE_CHANGE_CALLBACKS, *PVMB_CHANNEL_STATE_CHANGE_CALLBACKS;
````

## Members


`EvtChannelClosed`

The channel closed callback function.

`EvtChannelOpened`

The channel opened callback function.

`EvtChannelPostStarted`

The channel post started callback function.

`EvtChannelStarted`

The channel started callback function.

`EvtChannelSuspend`

The channel suspended callback funciton.

`Size`

Size of callbacks.

`Version`

The version.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |