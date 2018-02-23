---
UID: NE:ksproxy.FRAMING_PROP
title: FRAMING_PROP
author: windows-driver-content
description: "."
old-location: stream\framing_prop.htm
old-project: stream
ms.assetid: EE68F14D-F76D-4D98-99FB-BD3FB93B669A
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ksproxy/FramingProp_Ex, *PFRAMING_PROP, stream.framing_prop, ksproxy/FramingProp_Uninitialized, FramingProp_Old, FramingProp_Uninitialized, FramingProp_None, FRAMING_PROP enumeration [Streaming Media Devices], ksproxy/FRAMING_PROP, FRAMING_PROP, ksproxy/FramingProp_Old, FramingProp_Ex, ksproxy/FramingProp_None
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
-	FRAMING_PROP
product: Windows
targetos: Windows
req.typenames: FRAMING_PROP
---

# FRAMING_PROP Enumeration


## Syntax
````
typedef enum  { 
  FramingProp_Uninitialized,
  FramingProp_None,
  FramingProp_Old,
  FramingProp_Ex
} FRAMING_PROP;
````

## Constants

<table>
            
                <tr>
                    <td>FramingProp_Ex</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>FramingProp_None</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>FramingProp_Old</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>FramingProp_Uninitialized</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksproxy.h |