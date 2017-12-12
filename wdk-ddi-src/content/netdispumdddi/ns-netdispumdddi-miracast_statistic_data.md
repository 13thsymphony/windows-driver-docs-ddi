---
UID: NS.NETDISPUMDDDI.MIRACAST_STATISTIC_DATA
title: MIRACAST_STATISTIC_DATA
author: windows-driver-content
description: Contains Miracast statistics data that the user-mode display driver reports to the operating system.
old-location: display\miracast_statistic_data.htm
old-project: display
ms.assetid: 94D5C260-4076-4DB7-8ED3-E0549A872FEE
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: MIRACAST_STATISTIC_DATA, MIRACAST_STATISTIC_DATA
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
req.alt-api: MIRACAST_STATISTIC_DATA
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

# MIRACAST_STATISTIC_DATA structure



## -description
Contains Miracast statistics data that the user-mode display driver reports to the operating system.



## -syntax

````
typedef struct {
  MIRACAST_STATISTIC_TYPE StatisticType;
  union {
    struct {
      MIRACAST_CHUNK_INFO ChunkInfo;
    } EncodeComplete;
    struct {
      MIRACAST_CHUNK_ID ChunkId;
    } ChunkSent;
    struct {
      MIRACAST_PROTOCOL_EVENT Event;
    } ProtocolEvent;
  };
} MIRACAST_STATISTIC_DATA;
````


## -struct-fields

### -field StatisticType

The type of statistics data from the <a href="..\netdispumdddi\ne-netdispumdddi-miracast_statistic_type.md">MIRACAST_STATISTIC_TYPE</a> enumeration.


### -field EncodeComplete


### -field ChunkInfo

A <a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_info.md">MIRACAST_CHUNK_INFO</a> structure that provides info about an encode chunk that is identified by the <b>ChunkId</b> member.

</dd>
</dl>

### -field ChunkSent


### -field ChunkId

The identifier for this chunk, of type <a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_id.md">MIRACAST_CHUNK_ID</a>.

</dd>
</dl>

### -field ProtocolEvent


### -field Event

The type of protocol event, given as a value of the <a href="..\netdispumdddi\ne-netdispumdddi-miracast_protocol_event.md">MIRACAST_PROTOCOL_EVENT</a> enumeration.

</dd>
</dl>

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
<a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_info.md">MIRACAST_CHUNK_INFO</a>
</dt>
<dt>
<a href="..\netdispumdddi\ne-netdispumdddi-miracast_protocol_event.md">MIRACAST_PROTOCOL_EVENT</a>
</dt>
<dt>
<a href="..\netdispumdddi\ne-netdispumdddi-miracast_statistic_type.md">MIRACAST_STATISTIC_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20MIRACAST_STATISTIC_DATA structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

