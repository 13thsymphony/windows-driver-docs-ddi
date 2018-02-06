---
UID: NE:ksproxy.PIPE_STATE
title: PIPE_STATE
author: windows-driver-content
description: "."
old-location: stream\pipe_state.htm
old-project: stream
ms.assetid: A3053A39-5DB6-4DB8-89ED-63ABDB1CD16F
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PipeState_RangeNotFixed, ksproxy/PipeState_Finalized, ksproxy/PipeState_CompressionUnknown, PipeState_CompressionUnknown, ksproxy/PIPE_STATE, PipeState_RangeFixed, stream.pipe_state, PIPE_STATE enumeration [Streaming Media Devices], ksproxy/PipeState_RangeNotFixed, PIPE_STATE, PipeState_Finalized, PipeState_DontCare, ksproxy/PipeState_DontCare, ksproxy/PipeState_RangeFixed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksproxy.h
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
-	Ksproxy.h
apiname:
-	PIPE_STATE
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# PIPE_STATE Enumeration


## Syntax
````
typedef enum  { 
  PipeState_DontCare,
  PipeState_RangeNotFixed,
  PipeState_RangeFixed,
  PipeState_CompressionUnknown,
  PipeState_Finalized
} PIPE_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>PipeState_CompressionUnknown</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>PipeState_DontCare</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>PipeState_Finalized</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>PipeState_RangeFixed</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>PipeState_RangeNotFixed</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksproxy.h |