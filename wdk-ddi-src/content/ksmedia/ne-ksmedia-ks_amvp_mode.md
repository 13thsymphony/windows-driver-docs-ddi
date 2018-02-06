---
UID: NE:ksmedia.KS_AMVP_MODE
title: KS_AMVP_MODE
author: windows-driver-content
description: The KS_AMVP_MODE enumeration defines video port display modes.
old-location: stream\ks_amvp_mode.htm
old-project: stream
ms.assetid: 9464a17a-fa09-46c5-a4a7-d5cbd58deebd
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/KS_AMVP_MODE_SKIPODD, KS_AMVP_MODE enumeration [Streaming Media Devices], ksmedia/KS_AMVP_MODE_BOBINTERLEAVED, KS_AMVP_MODE_WEAVE, KS_AMVP_MODE_BOBNONINTERLEAVED, ksmedia/KS_AMVP_MODE_BOBNONINTERLEAVED, KS_AMVP_MODE, KS_AMVP_MODE_BOBINTERLEAVED, stream.ks_amvp_mode, ksmedia/KS_AMVP_MODE_SKIPEVEN, vidcapstruct_64634d5e-72a6-4300-9fa9-e1d6859f0813.xml, ksmedia/KS_AMVP_MODE, KS_AMVP_MODE_SKIPEVEN, KS_AMVP_MODE_SKIPODD, ksmedia/KS_AMVP_MODE_WEAVE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
apiname:
-	KS_AMVP_MODE
product: Windows
targetos: Windows
req.typenames: KS_AMVP_MODE
---

# KS_AMVP_MODE Enumeration
The KS_AMVP_MODE enumeration defines video port display modes.

## Syntax
````
typedef enum  { 
  KS_AMVP_MODE_WEAVE              = 0,
  KS_AMVP_MODE_BOBINTERLEAVED     = 1,
  KS_AMVP_MODE_BOBNONINTERLEAVED  = 2,
  KS_AMVP_MODE_SKIPEVEN           = 3,
  KS_AMVP_MODE_SKIPODD            = 4
} KS_AMVP_MODE;
````

## Constants

<table>
            
                <tr>
                    <td>KS_AMVP_MODE_BOBINTERLEAVED</td>
                    <td>Specifies the interleaved bob method to display video. In the interleaved bob mode, each field is displayed individually, and the gaps between fields are filled with interpolated values.</td>
                </tr>
            
                <tr>
                    <td>KS_AMVP_MODE_BOBNONINTERLEAVED</td>
                    <td>Specifies the non-interleaved bob method to display video.</td>
                </tr>
            
                <tr>
                    <td>KS_AMVP_MODE_SKIPEVEN</td>
                    <td>Specifies that even video fields should be skipped when displaying video.</td>
                </tr>
            
                <tr>
                    <td>KS_AMVP_MODE_SKIPODD</td>
                    <td>Specifies that odd video fields should be skipped when displaying video.</td>
                </tr>
            
                <tr>
                    <td>KS_AMVP_MODE_WEAVE</td>
                    <td>Specifies the weave method to display interlaced video. In the weave mode, alternating fields are combined to form a single frame.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |