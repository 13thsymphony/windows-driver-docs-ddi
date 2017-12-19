---
UID: NS.KSMEDIA.KSCAMERA_PERFRAMESETTING_CAP_HEADER
title: KSCAMERA_PERFRAMESETTING_CAP_HEADER
author: windows-driver-content
description: This structure contains the header information for the per frame settings capabilities.
old-location: stream\kscamera_perframesetting_cap_header.htm
old-project: stream
ms.assetid: 7478E83E-0657-4547-993A-84AECBB2562D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSCAMERA_PERFRAMESETTING_CAP_HEADER, PKSCAMERA_PERFRAMESETTING_CAP_HEADER, KSCAMERA_PERFRAMESETTING_CAP_HEADER, *PKSCAMERA_PERFRAMESETTING_CAP_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_PERFRAMESETTING_CAP_HEADER
req.alt-loc: Ksmedia.h
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

# KSCAMERA_PERFRAMESETTING_CAP_HEADER structure



## -description
This structure contains the header information for the per frame settings capabilities.



## -syntax

````
typedef struct {
  ULONG     Size;
  ULONG     ItemCount;
  ULONGLONG Flags;
} KSCAMERA_PERFRAMESETTING_CAP_HEADER, *PKSCAMERA_PERFRAMESETTING_CAP_HEADER;
````


## -struct-fields

### -field Size

The size of the entire capability payload, including this header, all the item headers, and the item payloads that follow.


### -field ItemCount

The number of capability items.


### -field Flags

Not used.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>