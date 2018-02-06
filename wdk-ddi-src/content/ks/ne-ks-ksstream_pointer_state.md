---
UID: NE:ks.KSSTREAM_POINTER_STATE
title: KSSTREAM_POINTER_STATE
author: windows-driver-content
description: "."
old-location: stream\ksstream_pointer_state.htm
old-project: stream
ms.assetid: E3DF002D-825C-4DF6-935F-53D73F12FE2E
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSSTREAM_POINTER_STATE_UNLOCKED, ks/KSSTREAM_POINTER_STATE_LOCKED, ks/KSSTREAM_POINTER_STATE, KSSTREAM_POINTER_STATE, ks/KSSTREAM_POINTER_STATE_UNLOCKED, KSSTREAM_POINTER_STATE enumeration [Streaming Media Devices], KSSTREAM_POINTER_STATE_LOCKED, stream.ksstream_pointer_state
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ks.h
apiname:
-	KSSTREAM_POINTER_STATE
product: Windows
targetos: Windows
req.typenames: KSSTREAM_POINTER_STATE
---

# KSSTREAM_POINTER_STATE Enumeration


## Syntax
````
typedef enum  { 
  KSSTREAM_POINTER_STATE_UNLOCKED  = 0,
  KSSTREAM_POINTER_STATE_LOCKED
} KSSTREAM_POINTER_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>KSSTREAM_POINTER_STATE_LOCKED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KSSTREAM_POINTER_STATE_UNLOCKED</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h |