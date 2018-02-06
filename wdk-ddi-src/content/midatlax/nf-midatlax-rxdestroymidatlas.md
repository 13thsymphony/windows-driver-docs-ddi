---
UID: NF:midatlax.RxDestroyMidAtlas
title: RxDestroyMidAtlas function
author: windows-driver-content
description: RxDestroyMidAtlas destroys an existing instance of a MID_ATLAS data structure and frees the allocated memory.
old-location: ifsk\rxdestroymidatlas.htm
old-project: ifsk
ms.assetid: 9d5c08c8-8306-46e3-b10b-eeefe473d340
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.rxdestroymidatlas, rxref_3a954108-5744-4b47-87b7-7553d64ec038.xml, RxDestroyMidAtlas function [Installable File System Drivers], RxDestroyMidAtlas, midatlax/RxDestroyMidAtlas
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
-	RxDestroyMidAtlas
product: Windows
targetos: Windows
req.typenames: "*PMCD_INIT_DATA, MCD_INIT_DATA"
---


# RxDestroyMidAtlas function
<b>RxDestroyMidAtlas</b> destroys an existing instance of a MID_ATLAS data structure and frees the allocated memory.

## Syntax

````
VOID RxDestroyMidAtlas(
   PRX_MID_ATLAS       pMidAtlas,
   PCONTEXT_DESTRUCTOR pContextDestructor
);
````

## Parameters

`MidAtlas`

TBD

`ContextDestructor`

TBD


## Return Value

None

## Remarks

RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is part of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>.

<b>RxDestroyMidAtlas</b> destroys a MID_ATLAS data structure previously created by a call to <b>RxCreateMidAtlas</b>. As a side effect, <b>RxDestroyMidAtlas</b> invokes the passed in context destructor on every valid context in the MID_ATLAS.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | midatlax.h (include Midatlax.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\midatlax\nf-midatlax-rxreassociatemid.md">RxReassociateMid</a>

<a href="..\midatlax\nf-midatlax-rxcreatemidatlas.md">RxCreateMidAtlas</a>

<a href="..\midatlax\nf-midatlax-rxmapanddissociatemidfromcontext.md">RxMapAndDissociateMidFromContext</a>

<a href="..\midatlax\nf-midatlax-rxmapmidtocontext.md">RxMapMidToContext</a>

<a href="..\midatlax\nf-midatlax-rxassociatecontextwithmid.md">RxAssociateContextWithMid</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxDestroyMidAtlas function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>