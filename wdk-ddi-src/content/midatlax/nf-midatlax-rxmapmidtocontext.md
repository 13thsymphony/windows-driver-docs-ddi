---
UID: NF:midatlax.RxMapMidToContext
title: RxMapMidToContext function
author: windows-driver-content
description: RxMapMidToContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure.
old-location: ifsk\rxmapmidtocontext.htm
old-project: ifsk
ms.assetid: e0625c27-6de9-401f-a6bd-52697c4a57c0
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: RxMapMidToContext, rxref_e7a11999-7ace-4154-91aa-28dc99a83790.xml, RxMapMidToContext function [Installable File System Drivers], midatlax/RxMapMidToContext, ifsk.rxmapmidtocontext
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
-	RxMapMidToContext
product: Windows
targetos: Windows
req.typenames: "*PMCD_INIT_DATA, MCD_INIT_DATA"
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
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\midatlax\nf-midatlax-rxreassociatemid.md">RxReassociateMid</a>



<a href="..\midatlax\nf-midatlax-rxdestroymidatlas.md">RxDestroyMidAtlas</a>



<a href="..\midatlax\nf-midatlax-rxmapanddissociatemidfromcontext.md">RxMapAndDissociateMidFromContext</a>



<a href="..\midatlax\nf-midatlax-rxassociatecontextwithmid.md">RxAssociateContextWithMid</a>



<a href="..\midatlax\nf-midatlax-rxcreatemidatlas.md">RxCreateMidAtlas</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxMapMidToContext function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>