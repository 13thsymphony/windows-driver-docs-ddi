---
UID : NS:1394._IRB_REQ_ISOCH_STOP
title : "_IRB_REQ_ISOCH_STOP"
author : windows-driver-content
description : This structure contains the field necessary to carry out a IsochStop request.
old-location : ieee\irb_req_isoch_stop.htm
old-project : IEEE
ms.assetid : 1400FAC6-DD4E-4E8E-A0ED-C59B700F0672
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IRB_REQ_ISOCH_STOP, IRB_REQ_ISOCH_STOP structure [Buses], 1394/IRB_REQ_ISOCH_STOP, _IRB_REQ_ISOCH_STOP, IEEE.irb_req_isoch_stop
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
req.typenames : IRB_REQ_ISOCH_STOP
---

# _IRB_REQ_ISOCH_STOP structure
This structure contains the field necessary to carry out a IsochStop request.

## Syntax
````
typedef struct _IRB_REQ_ISOCH_STOP {
  HANDLE hResource;
  ULONG  fulFlags;
} IRB_REQ_ISOCH_STOP;
````

## Members


`fulFlags`

Reserved. Device drivers should set this member to zero.

`hResource`

Specifies the resource handle for the channel on which to stop isochronous operations.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h |