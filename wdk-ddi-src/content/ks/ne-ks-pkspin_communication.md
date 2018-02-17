---
UID: NE:ks.PKSPIN_COMMUNICATION
title: "*PKSPIN_COMMUNICATION"
author: windows-driver-content
description: "."
old-location: stream\kspin_communication.htm
old-project: stream
ms.assetid: DBBEEE9D-82C1-4387-AA6D-C5D86EDB138C
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPIN_COMMUNICATION_SOURCE, KSPIN_COMMUNICATION, KSPIN_COMMUNICATION_SINK, ks/KSPIN_COMMUNICATION_NONE, PKSPIN_COMMUNICATION enumeration pointer [Streaming Media Devices], ks/KSPIN_COMMUNICATION_SOURCE, ks/PKSPIN_COMMUNICATION, stream.kspin_communication, KSPIN_COMMUNICATION_BOTH, ks/KSPIN_COMMUNICATION_BOTH, KSPIN_COMMUNICATION_BRIDGE, ks/KSPIN_COMMUNICATION_SINK, ks/KSPIN_COMMUNICATION, ks/KSPIN_COMMUNICATION_BRIDGE, KSPIN_COMMUNICATION enumeration [Streaming Media Devices], *PKSPIN_COMMUNICATION, PKSPIN_COMMUNICATION, KSPIN_COMMUNICATION_NONE
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
-	KSPIN_COMMUNICATION
product: Windows
targetos: Windows
req.typenames: "*PKSPIN_COMMUNICATION, KSPIN_COMMUNICATION"
---

# *PKSPIN_COMMUNICATION Enumeration


## Syntax
````
typedef enum  { 
  KSPIN_COMMUNICATION_NONE,
  KSPIN_COMMUNICATION_SINK,
  KSPIN_COMMUNICATION_SOURCE,
  KSPIN_COMMUNICATION_BOTH,
  KSPIN_COMMUNICATION_BRIDGE
} KSPIN_COMMUNICATION, *PKSPIN_COMMUNICATION;
````

## Constants

<table>
            
                <tr>
                    <td>KSPIN_COMMUNICATION_BOTH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KSPIN_COMMUNICATION_BRIDGE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KSPIN_COMMUNICATION_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KSPIN_COMMUNICATION_SINK</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KSPIN_COMMUNICATION_SOURCE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h |