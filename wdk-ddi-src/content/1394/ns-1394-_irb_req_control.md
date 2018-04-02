---
UID: NS:1394._IRB_REQ_CONTROL
title: "_IRB_REQ_CONTROL"
author: windows-driver-content
description: This structure contains the fields necessary for the 1394 bus driver to carry out a control request.
old-location: ieee\irb_req_control.htm
old-project: IEEE
ms.assetid: F0ABD318-AC63-40D5-B94E-BD6FEA1A57AC
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1394/IRB_REQ_CONTROL, IEEE.irb_req_control, IRB_REQ_CONTROL, IRB_REQ_CONTROL structure [Buses], _IRB_REQ_CONTROL
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
-	IRB_REQ_CONTROL
product: Windows
targetos: Windows
req.typenames: IRB_REQ_CONTROL
---

# _IRB_REQ_CONTROL structure
This structure contains the fields necessary for the 1394 bus driver to carry out a control request.

## Syntax
```
typedef struct _IRB_REQ_CONTROL {
  ULONG ulIoControlCode;
  PMDL  pInBuffer;
  ULONG ulInBufferLength;
  PMDL  pOutBuffer;
  ULONG ulOutBufferLength;
  ULONG BytesReturned;
} IRB_REQ_CONTROL;
```

## Members


`ulIoControlCode`

Specifies the control code used in this request. Vendors should make these control codes unique, so that they do not overlap.

`pInBuffer`

Points to an MDL that describes the input buffer. The input buffer contains user-defined information.

`ulInBufferLength`

Specifies the length of the input buffer.

`pOutBuffer`

Points to an MDL that describes the output buffer. The output buffer contains user-defined information.

`ulOutBufferLength`

Specifies the length of the output buffer.

`BytesReturned`

Specifies the number of bytes returned.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h |