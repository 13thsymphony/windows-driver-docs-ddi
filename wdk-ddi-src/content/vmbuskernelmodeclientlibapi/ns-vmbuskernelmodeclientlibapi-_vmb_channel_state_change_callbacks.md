---
UID: NS.VMBUSKERNELMODECLIENTLIBAPI._VMB_CHANNEL_STATE_CHANGE_CALLBACKS
title: _VMB_CHANNEL_STATE_CHANGE_CALLBACKS
author: windows-driver-content
description: The VMB_CHANNEL_STATE_CHANGE_CALLBACKS structure contains callback functions that relate to the state changes for a channel.
old-location: netvista\vmb_channel_state_change_callbacks.htm
old-project: netvista
ms.assetid: 01A9A947-76F0-407C-8480-B2721A9A8A7B
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _VMB_CHANNEL_STATE_CHANGE_CALLBACKS, *PVMB_CHANNEL_STATE_CHANGE_CALLBACKS, VMB_CHANNEL_STATE_CHANGE_CALLBACKS
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
req.alt-api: VMB_CHANNEL_STATE_CHANGE_CALLBACKS
req.alt-loc: VmbusKernelModeClientLibApi.h
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
req.product: Windows 10 or later.
---

# _VMB_CHANNEL_STATE_CHANGE_CALLBACKS structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]
The <b>VMB_CHANNEL_STATE_CHANGE_CALLBACKS</b> structure contains callback functions that relate to the state changes for a channel. 


## -syntax

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


## -struct-fields

### -field Version

The version.

### -field Size

Size of callbacks.

### -field EvtChannelOpened

The channel opened callback function.

### -field EvtChannelClosed

The channel closed callback function.

### -field EvtChannelSuspend

The channel suspended callback funciton. 

### -field EvtChannelStarted

The channel started callback function. 

### -field EvtChannelPostStarted

The channel post started callback function.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
</dl>
</td>
</tr>
</table>