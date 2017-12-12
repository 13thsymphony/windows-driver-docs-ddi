---
UID: NS.D3DKMTHK._D3DKMT_DEVICEPRESENT_QUEUE_STATE
title: _D3DKMT_DEVICEPRESENT_QUEUE_STATE
author: windows-driver-content
description: A structure that holds information on the queue state of a hardware device.
old-location: display\d3dkmt_devicepresent_queue_state.htm
old-project: display
ms.assetid: 0DB9F0ED-D0A9-4A8A-8E27-BC50DEDB0BD5
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMT_DEVICEPRESENT_QUEUE_STATE, D3DKMT_DEVICEPRESENT_QUEUE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_DEVICEPRESENT_QUEUE_STATE
req.alt-loc: d3dkmthk.h
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
---

# _D3DKMT_DEVICEPRESENT_QUEUE_STATE structure



## -description
A structure that holds information on the queue state of a hardware device.



## -syntax

````
typedef struct _D3DKMT_DEVICEPRESENT_QUEUE_STATE {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  BOOLEAN                        bQueuedPresentLimitReached;
} D3DKMT_DEVICEPRESENT_QUEUE_STATE;
````


## -struct-fields

### -field VidPnSourceId

Indicates the present source id.


### -field bQueuedPresentLimitReached

Indicates whether the queued present limit has been reached.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h</dt>
</dl>
</td>
</tr>
</table>