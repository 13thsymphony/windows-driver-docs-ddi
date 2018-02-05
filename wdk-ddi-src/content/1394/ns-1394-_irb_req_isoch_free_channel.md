---
UID : NS:1394._IRB_REQ_ISOCH_FREE_CHANNEL
title : "_IRB_REQ_ISOCH_FREE_CHANNEL"
author : windows-driver-content
description : This structure contains the fields required to carry out a IsochFreeChannel request.
old-location : ieee\irb_req_isoch_free_channel.htm
old-project : IEEE
ms.assetid : 949D165B-1F42-40EA-B050-38847E14B968
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IEEE.irb_req_isoch_free_channel, _IRB_REQ_ISOCH_FREE_CHANNEL, IRB_REQ_ISOCH_FREE_CHANNEL, IRB_REQ_ISOCH_FREE_CHANNEL structure [Buses], 1394/IRB_REQ_ISOCH_FREE_CHANNEL
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : 1394.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : IRB_REQ_ISOCH_FREE_CHANNEL
---

# _IRB_REQ_ISOCH_FREE_CHANNEL structure
This structure contains the fields required to carry out a IsochFreeChannel request.

## Syntax
````
typedef struct _IRB_REQ_ISOCH_FREE_CHANNEL {
  ULONG nChannel;
} IRB_REQ_ISOCH_FREE_CHANNEL;
````

## Members


`nChannel`

Specifies which allocated channel to release.

## Remarks
If successful, the bus driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS, and the isochronous channel is returned to the pool of available channels.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h |