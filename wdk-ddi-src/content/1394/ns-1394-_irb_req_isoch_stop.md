---
UID: NS:1394._IRB_REQ_ISOCH_STOP
title: "_IRB_REQ_ISOCH_STOP"
author: windows-driver-content
description: This structure contains the field necessary to carry out a IsochStop request.
old-location: ieee\irb_req_isoch_stop.htm
old-project: IEEE
ms.assetid: 1400FAC6-DD4E-4E8E-A0ED-C59B700F0672
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1394/IRB_REQ_ISOCH_STOP, IEEE.irb_req_isoch_stop, IRB_REQ_ISOCH_STOP, IRB_REQ_ISOCH_STOP structure [Buses], _IRB_REQ_ISOCH_STOP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
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
-	1394.h
api_name:
-	IRB_REQ_ISOCH_STOP
product: Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_STOP
---

# _IRB_REQ_ISOCH_STOP structure
This structure contains the field necessary to carry out a IsochStop request.

## Syntax
```
typedef struct _IRB_REQ_ISOCH_STOP {
  HANDLE hResource;
  ULONG  fulFlags;
} IRB_REQ_ISOCH_STOP;
```

## Members


`hResource`

Specifies the resource handle for the channel on which to stop isochronous operations.

`fulFlags`

Reserved. Device drivers should set this member to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h |