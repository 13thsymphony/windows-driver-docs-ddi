---
UID: NE:ks.KSCOMPLETION_INVOCATION
title: KSCOMPLETION_INVOCATION
author: windows-driver-content
description: "."
old-location: stream\kscompletion_invocation.htm
old-project: stream
ms.assetid: 2BD1A2F8-BAA2-40A3-9C97-667780A6F395
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KSCOMPLETION_INVOCATION, KSCOMPLETION_INVOCATION enumeration [Streaming Media Devices], KsInvokeOnCancel, KsInvokeOnError, KsInvokeOnSuccess, ks/KSCOMPLETION_INVOCATION, ks/KsInvokeOnCancel, ks/KsInvokeOnError, ks/KsInvokeOnSuccess, stream.kscompletion_invocation
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ks.h
api_name:
-	KSCOMPLETION_INVOCATION
product: Windows
targetos: Windows
req.typenames: KSCOMPLETION_INVOCATION
---

# KSCOMPLETION_INVOCATION Enumeration


## Syntax
```
typedef enum KSCOMPLETION_INVOCATION {
  KsInvokeOnSuccess  ,
  KsInvokeOnError    ,
  KsInvokeOnCancel
} ;
```

## Constants

<table>
            
                <tr>
                    <td>KsInvokeOnSuccess</td>
                    <td>Invokes the completion routine on success.</td>
                </tr>
            
                <tr>
                    <td>KsInvokeOnError</td>
                    <td>Invokes the completion routine on error.</td>
                </tr>
            
                <tr>
                    <td>KsInvokeOnCancel</td>
                    <td>Invokes the completion routine on cancellation.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h |