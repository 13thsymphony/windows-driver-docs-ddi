---
UID: NS:ndis._NET_BUFFER_HEADER
title: _NET_BUFFER_HEADER
author: windows-driver-content
description: The NET_BUFFER_HEADER structure specifies header information for the NET_BUFFER structure.
old-location: netvista\net_buffer_header.htm
old-project: netvista
ms.assetid: db7277d0-9671-4680-84d4-d3415ce3922f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NET_BUFFER_HEADER, NET_BUFFER_HEADER, *PNET_BUFFER_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NET_BUFFER_HEADER
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.typenames: NET_BUFFER_HEADER, *PNET_BUFFER_HEADER
---

# _NET_BUFFER_HEADER structure



## -description
The NET_BUFFER_HEADER structure specifies header information for the 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure.



## -syntax

````
typedef union _NET_BUFFER_HEADER {
  NET_BUFFER_DATA NetBufferData;
  SLIST_HEADER    Link;
} NET_BUFFER_HEADER, *PNET_BUFFER_HEADER;
````


## -struct-fields

### -field NetBufferData

A 
     <a href="..\ndis\ns-ndis-_net_buffer_data.md">NET_BUFFER_DATA</a> structure.


### -field Link

Reserved for NDIS.


## -remarks
NDIS maintains the information in the NET_BUFFER_HEADER union.


## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_data.md">NET_BUFFER_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_BUFFER_HEADER union%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

