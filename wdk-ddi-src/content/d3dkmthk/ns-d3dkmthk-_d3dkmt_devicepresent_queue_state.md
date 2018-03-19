---
UID: NS:d3dkmthk._D3DKMT_DEVICEPRESENT_QUEUE_STATE
title: "_D3DKMT_DEVICEPRESENT_QUEUE_STATE"
author: windows-driver-content
description: A structure that holds information on the queue state of a hardware device.
old-location: display\d3dkmt_devicepresent_queue_state.htm
old-project: display
ms.assetid: 0DB9F0ED-D0A9-4A8A-8E27-BC50DEDB0BD5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_DEVICEPRESENT_QUEUE_STATE, D3DKMT_DEVICEPRESENT_QUEUE_STATE structure [Display Devices], _D3DKMT_DEVICEPRESENT_QUEUE_STATE, d3dkmthk/D3DKMT_DEVICEPRESENT_QUEUE_STATE, display.d3dkmt_devicepresent_queue_state
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
-	d3dkmthk.h
api_name:
-	D3DKMT_DEVICEPRESENT_QUEUE_STATE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DEVICEPRESENT_QUEUE_STATE
---

# _D3DKMT_DEVICEPRESENT_QUEUE_STATE structure
A structure that holds information on the queue state of a hardware device.

## Syntax
````
typedef struct _D3DKMT_DEVICEPRESENT_QUEUE_STATE {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  BOOLEAN                        bQueuedPresentLimitReached;
} D3DKMT_DEVICEPRESENT_QUEUE_STATE;
````

## Members


`VidPnSourceId`

Indicates the present source id.

`bQueuedPresentLimitReached`

Indicates whether the queued present limit has been reached.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |