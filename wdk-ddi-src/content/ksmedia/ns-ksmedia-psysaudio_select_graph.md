---
UID: NS.KSMEDIA.PSYSAUDIO_SELECT_GRAPH
title: PSYSAUDIO_SELECT_GRAPH
author: windows-driver-content
description: The SYSAUDIO_SELECT_GRAPH structure is used to specify a graph that includes an optional node such as an AEC control.
old-location: audio\sysaudio_select_graph.htm
old-project: audio
ms.assetid: f114e8ef-4fb7-4fdd-9c83-d8e74c91190e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PSYSAUDIO_SELECT_GRAPH, SYSAUDIO_SELECT_GRAPH, *PSYSAUDIO_SELECT_GRAPH
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
req.alt-api: SYSAUDIO_SELECT_GRAPH
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

# PSYSAUDIO_SELECT_GRAPH structure



## -description
The SYSAUDIO_SELECT_GRAPH structure is used to specify a graph that includes an optional node such as an AEC control.



## -syntax

````
typedef struct {
  KSPROPERTY Property;
  ULONG      PinId;
  ULONG      NodeId;
  ULONG      Flags;
  ULONG      Reserved;
} SYSAUDIO_SELECT_GRAPH, *PSYSAUDIO_SELECT_GRAPH;
````


## -struct-fields

### -field Property

Specifies the property to get or set. This parameter is a structure of type <a href="stream.ksproperty">KSPROPERTY</a>.


### -field PinId

Specifies the SysAudio starting pin ID for the graph.


### -field NodeId

Specifies the SysAudio node ID to be included in the graph.


### -field Flags

No flag bits are defined. Set to zero.


### -field Reserved

Reserved. Set to zero. 


## -remarks


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

## -see-also
<dl>
<dt>
<a href="stream.ksproperty">KSPROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537428">KSPROPERTY_SYSAUDIO_SELECT_GRAPH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20SYSAUDIO_SELECT_GRAPH structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

