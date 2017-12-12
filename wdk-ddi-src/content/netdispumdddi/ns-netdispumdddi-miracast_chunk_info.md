---
UID: NS.NETDISPUMDDDI.MIRACAST_CHUNK_INFO
title: MIRACAST_CHUNK_INFO
author: windows-driver-content
description: Contains info about a specified wireless display (Miracast) encode chunk.
old-location: display\miracast_chunk_info.htm
old-project: display
ms.assetid: 7015cbc5-f8d1-4e06-bb02-2706a26877f0
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: MIRACAST_CHUNK_INFO, MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MIRACAST_CHUNK_INFO
req.alt-loc: Netdispumdddi.h
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

# MIRACAST_CHUNK_INFO structure



## -description
Contains info about a specified wireless display (Miracast) encode chunk.



## -syntax

````
typedef struct {
  MIRACAST_CHUNK_TYPE ChunkType;
  MIRACAST_CHUNK_ID   ChunkId;
  UINT                ProcessingTime;
  UINT                EncodeRate;
} MIRACAST_CHUNK_INFO;
````


## -struct-fields

### -field ChunkType

The type of chunk that is to be processed, specified as a <a href="..\netdispumdddi\ne-netdispumdddi-miracast_chunk_type.md">MIRACAST_CHUNK_TYPE</a> enumeration value.


### -field ChunkId

The identifier for this chunk, of type <a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_id.md">MIRACAST_CHUNK_ID</a>.


### -field ProcessingTime

The time, in microseconds, that it took to process this chunk.


### -field EncodeRate

The encode bit rate, in kilobits per second, that the user-mode driver reported for this chunk.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Netdispumdddi.h (include Netdispumdddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_id.md">MIRACAST_CHUNK_ID</a>
</dt>
<dt>
<a href="..\netdispumdddi\ne-netdispumdddi-miracast_chunk_type.md">MIRACAST_CHUNK_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20MIRACAST_CHUNK_INFO structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

