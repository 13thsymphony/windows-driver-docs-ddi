---
UID: NE:poscx._POS_CX_EVENT_PRIORITY
title: "_POS_CX_EVENT_PRIORITY"
author: windows-driver-content
description: The POS_CX_EVENT_PRIORITY defines the importance of the event and the order it will be delivered to the client application.
old-location: pos\pos_cx_event_priority.htm
old-project: pos
ms.assetid: 835DC1E4-2D49-4D43-A545-5D4288412EC6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: POS_CX_EVENT_PRIORITY_DATA, POS_CX_EVENT_PRIORITY_INVALID, POS_CX_EVENT_PRIORITY enumeration, poscx/POS_CX_EVENT_PRIORITY_INVALID, poscx/POS_CX_EVENT_PRIORITY_DATA, POS_CX_EVENT_PRIORITY, POS_CX_EVENT_PRIORITY_CONTROL, _POS_CX_EVENT_PRIORITY, poscx/POS_CX_EVENT_PRIORITY, pos.pos_cx_event_priority, poscx/POS_CX_EVENT_PRIORITY_CONTROL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: poscx.h
req.include-header: Poscx.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	poscx.h
apiname:
-	POS_CX_EVENT_PRIORITY
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---

# _POS_CX_EVENT_PRIORITY Enumeration
The POS_CX_EVENT_PRIORITY defines the importance of the event and the order it will be delivered to the client application.

## Syntax
````
typedef enum _POS_CX_EVENT_PRIORITY { 
  POS_CX_EVENT_PRIORITY_INVALID  = 0,
  POS_CX_EVENT_PRIORITY_DATA     = 1,
  POS_CX_EVENT_PRIORITY_CONTROL  = 2
} POS_CX_EVENT_PRIORITY;
````

## Constants

<table>
            
                <tr>
                    <td>POS_CX_EVENT_PRIORITY__MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>POS_CX_EVENT_PRIORITY_CONTROL</td>
                    <td>Control level priority delivered in FIFO.</td>
                </tr>
            
                <tr>
                    <td>POS_CX_EVENT_PRIORITY_DATA</td>
                    <td>Data level priority delivered in FIFO.</td>
                </tr>
            
                <tr>
                    <td>POS_CX_EVENT_PRIORITY_INVALID</td>
                    <td>Invalid priority. This value should not be used.</td>
                </tr>
</table>

    ## Remarks

        <div class="alert"><b>Note</b>  PosCx will deliver all Control level events before Data level events.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | poscx.h (include Poscx.h) |