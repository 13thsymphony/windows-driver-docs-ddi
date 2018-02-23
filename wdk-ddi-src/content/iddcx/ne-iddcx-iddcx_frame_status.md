---
UID: NE:iddcx.IDDCX_FRAME_STATUS
title: IDDCX_FRAME_STATUS
author: windows-driver-content
description: Defines the processing status of the frame.
old-location: display\iddcx_frame_status.htm
old-project: display
ms.assetid: 437050ae-d1b7-48ce-9955-98f1d1b2e15a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IDDCX_FRAME_STATUS_DROPPED, IDDCX_FRAME_STATUS_ERROR, iddcx/IDDCX_FRAME_STATUS, iddcx/IDDCX_FRAME_STATUS_UNINITIALIZED, IDDCX_FRAME_STATUS, display.iddcx_frame_status, iddcx/IDDCX_FRAME_STATUS_DROPPED, iddcx/IDDCX_FRAME_STATUS_ERROR, IDDCX_FRAME_STATUS enumeration [Display Devices], IDDCX_FRAME_STATUS_UNINITIALIZED, iddcx/IDDCX_FRAME_STATUS_COMPLETED, IDDCX_FRAME_STATUS_COMPLETED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iddcx.h
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
req.irql: "_requires_same_"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iddcx.h
apiname:
-	IDDCX_FRAME_STATUS
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_FRAME_STATUS Enumeration
Defines the processing status of the frame.

## Syntax
````
typedef enum _IDDCX_FRAME_STATUS { 
  IDDCX_FRAME_STATUS_UNINITIALIZED  = 0,
  IDDCX_FRAME_STATUS_COMPLETED      = 1,
  IDDCX_FRAME_STATUS_DROPPED        = 2,
  IDDCX_FRAME_STATUS_ERROR          = 3
} IDDCX_FRAME_STATUS;
````

## Constants

<table>
            
                <tr>
                    <td>IDDCX_FRAME_STATUS_COMPLETED</td>
                    <td>Indicates that the frame was processed completely and sent to the device</td>
                </tr>
            
                <tr>
                    <td>IDDCX_FRAME_STATUS_DROPPED</td>
                    <td>Indicates that the driver stopped processing this frame to start on a newer frame. This normally happens if it is taking a long time to process/transmit the frame</td>
                </tr>
            
                <tr>
                    <td>IDDCX_FRAME_STATUS_ERROR</td>
                    <td>Indicates that the driver stopped processing this frame because the driver hit an internal error</td>
                </tr>
            
                <tr>
                    <td>IDDCX_FRAME_STATUS_UNINITIALIZED</td>
                    <td>Indicates that an <b>IDDCX_FRAME_STATUS</b> variable has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>UINT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |