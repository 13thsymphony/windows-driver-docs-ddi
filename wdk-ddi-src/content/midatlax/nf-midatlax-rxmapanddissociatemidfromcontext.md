---
UID: NF:midatlax.RxMapAndDissociateMidFromContext
title: RxMapAndDissociateMidFromContext function
author: windows-driver-content
description: RxMapAndDissociateMidFromContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure and then disassociates the MID from the context.
old-location: ifsk\rxmapanddissociatemidfromcontext.htm
old-project: ifsk
ms.assetid: e9021983-8a01-4262-ae3f-c265948d5a2c
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: RxMapAndDissociateMidFromContext function [Installable File System Drivers], midatlax/RxMapAndDissociateMidFromContext, rxref_919dabed-ac8c-4495-8709-8fb45280e16f.xml, RxMapAndDissociateMidFromContext, ifsk.rxmapanddissociatemidfromcontext
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	midatlax.h
apiname:
-	RxMapAndDissociateMidFromContext
product: Windows
targetos: Windows
req.typenames: "*PMCD_INIT_DATA, MCD_INIT_DATA"
---


# RxMapAndDissociateMidFromContext function
<b>RxMapAndDissociateMidFromContext</b> maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure and then disassociates the MID from the context.

## Syntax

````
NTSTATUS RxMapAndDissociateMidFromContext(
   PRX_MID_ATLAS pMidAtlas,
   USHORT        Mid,
   PVOID         *pContextPointer
);
````

## Parameters

`MidAtlas`

TBD

`Mid`

The multiplex ID to be mapped.

`ContextPointer`

TBD


## Return Value

<a href="..\midatlax\nf-midatlax-rxreassociatemid.md">RxReassociateMid</a>
      always returns STATUS_SUCCESS. 

The returned <i>pContextPointer</i> parameter is a pointer to the associated context, or a <b>NULL</b> if no context was associated with this MID.

## Remarks

RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is a component of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>. A MID_MAP data structure is allocated and used for mapping MIDs to RX_CONTEXT data structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | midatlax.h (include Midatlax.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\midatlax\nf-midatlax-rxassociatecontextwithmid.md">RxAssociateContextWithMid</a>



<a href="..\midatlax\nf-midatlax-rxreassociatemid.md">RxReassociateMid</a>



<a href="..\midatlax\nf-midatlax-rxmapmidtocontext.md">RxMapMidToContext</a>



<a href="..\midatlax\nf-midatlax-rxdestroymidatlas.md">RxDestroyMidAtlas</a>



<a href="..\midatlax\nf-midatlax-rxcreatemidatlas.md">RxCreateMidAtlas</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxMapAndDissociateMidFromContext function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>