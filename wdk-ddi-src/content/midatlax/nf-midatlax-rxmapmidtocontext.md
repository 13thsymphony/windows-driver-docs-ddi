---
UID: NF:midatlax.RxMapMidToContext
title: RxMapMidToContext function
author: windows-driver-content
description: RxMapMidToContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure.
old-location: ifsk\rxmapmidtocontext.htm
old-project: ifsk
ms.assetid: e0625c27-6de9-401f-a6bd-52697c4a57c0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxMapMidToContext, RxMapMidToContext function [Installable File System Drivers], ifsk.rxmapmidtocontext, midatlax/RxMapMidToContext, rxref_e7a11999-7ace-4154-91aa-28dc99a83790.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: midatlax.h
req.include-header: Midatlax.h
req.target-type: Desktop
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	midatlax.h
api_name:
-	RxMapMidToContext
product: Windows
targetos: Windows
req.typenames: MCD_INIT_DATA, *PMCD_INIT_DATA
---


# RxMapMidToContext function
<b>RxMapMidToContext</b> maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure.

## Syntax

````
PVOID RxMapMidToContext(
   PRX_MID_ATLAS pMidAtlas,
   USHORT        Mid
);
````

## Parameters

`MidAtlas`

TBD

`Mid`

The multiplex ID to be mapped.


## Return Value

<b>RxMapMidToContext</b> returns a pointer to the associated context, or <b>NULL</b> if none exists.

## Remarks

RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is a component of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>. A MID_MAP data structure is allocated and used for mapping MIDs to RX_CONTEXT data structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | midatlax.h (include Midatlax.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\midatlax\nf-midatlax-rxreassociatemid.md">RxReassociateMid</a>



<a href="..\midatlax\nf-midatlax-rxdestroymidatlas.md">RxDestroyMidAtlas</a>



<a href="..\midatlax\nf-midatlax-rxmapanddissociatemidfromcontext.md">RxMapAndDissociateMidFromContext</a>



<a href="..\midatlax\nf-midatlax-rxcreatemidatlas.md">RxCreateMidAtlas</a>



<a href="..\midatlax\nf-midatlax-rxassociatecontextwithmid.md">RxAssociateContextWithMid</a>