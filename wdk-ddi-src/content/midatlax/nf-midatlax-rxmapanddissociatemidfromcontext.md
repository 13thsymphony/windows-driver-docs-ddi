---
UID: NF.midatlax.RxMapAndDissociateMidFromContext
title: RxMapAndDissociateMidFromContext function
author: windows-driver-content
description: RxMapAndDissociateMidFromContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure and then disassociates the MID from the context.
old-location: ifsk\rxmapanddissociatemidfromcontext.htm
old-project: ifsk
ms.assetid: e9021983-8a01-4262-ae3f-c265948d5a2c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RxMapAndDissociateMidFromContext
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
req.alt-api: RxMapAndDissociateMidFromContext
req.alt-loc: midatlax.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
---

# RxMapAndDissociateMidFromContext function



## -description
<b>RxMapAndDissociateMidFromContext</b> maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure and then disassociates the MID from the context. 



## -syntax

````
NTSTATUS RxMapAndDissociateMidFromContext(
   PRX_MID_ATLAS pMidAtlas,
   USHORT        Mid,
   PVOID         *pContextPointer
);
````


## -parameters

### -param pMidAtlas 

A pointer to the MID_ATLAS structure.


### -param Mid 

The multiplex ID to be mapped.


### -param pContextPointer 

A pointer that will hold the context for this MID on exit.


## -returns

<a href="ifsk.rxreassociatemid">RxReassociateMid</a>
      always returns STATUS_SUCCESS. 

The returned <i>pContextPointer</i> parameter is a pointer to the associated context, or a <b>NULL</b> if no context was associated with this MID.


## -remarks
RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is a component of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>. A MID_MAP data structure is allocated and used for mapping MIDs to RX_CONTEXT data structures. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Midatlax.h (include Midatlax.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.rxassociatecontextwithmid">RxAssociateContextWithMid</a>
</dt>
<dt>
<a href="ifsk.rxcreatemidatlas">RxCreateMidAtlas</a>
</dt>
<dt>
<a href="ifsk.rxdestroymidatlas">RxDestroyMidAtlas</a>
</dt>
<dt>
<a href="ifsk.rxmapmidtocontext">RxMapMidToContext</a>
</dt>
<dt>
<a href="ifsk.rxreassociatemid">RxReassociateMid</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxMapAndDissociateMidFromContext function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

