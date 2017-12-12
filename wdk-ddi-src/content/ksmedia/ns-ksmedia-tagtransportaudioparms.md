---
UID: NS.KSMEDIA.TAGTRANSPORTAUDIOPARMS
title: tagTRANSPORTAUDIOPARMS
author: windows-driver-content
description: The TRANSPORTAUDIOPARMS structure is defined but not used.
old-location: stream\transportaudioparms.htm
old-project: stream
ms.assetid: 591ef01a-1a89-454a-ab58-a76813a9d4c2
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: tagTRANSPORTAUDIOPARMS, *PTRANSPORTAUDIOPARMS, TRANSPORTAUDIOPARMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TRANSPORTAUDIOPARMS
req.alt-loc: ksmedia.h
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
---

# tagTRANSPORTAUDIOPARMS structure



## -description
The TRANSPORTAUDIOPARMS structure is defined but not used.



## -syntax

````
typedef struct tagTRANSPORTAUDIOPARMS {
  LONG EnableOutput;
  LONG EnableRecord;
  LONG EnableSelsync;
  LONG Input;
  LONG MonitorSource;
} TRANSPORTAUDIOPARMS, *PTRANSPORTAUDIOPARMS;
````


## -struct-fields

### -field EnableOutput

Specifies the enable audio output. The default is ED_AUDIO_ALL.


### -field EnableRecord

Specifies the enable audio record. The default is zero.


### -field EnableSelsync

Specifies the selsync.


### -field Input

Specifies the audio input to use. For example, specify zero to use the first (zeroth) audio input.


### -field MonitorSource

Indicates the monitor source. The default is zero.


## -remarks
Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>