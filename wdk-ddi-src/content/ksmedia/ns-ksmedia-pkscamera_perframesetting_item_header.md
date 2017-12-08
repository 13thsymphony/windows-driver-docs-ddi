---
UID: NS.KSMEDIA.PKSCAMERA_PERFRAMESETTING_ITEM_HEADER
title: PKSCAMERA_PERFRAMESETTING_ITEM_HEADER
author: windows-driver-content
description: This structure contains the header information for a per-frame settings item.
old-location: stream\kscamera_perframesetting_item_header.htm
old-project: stream
ms.assetid: A550E674-50CA-4956-8422-16875E29D04B
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSCAMERA_PERFRAMESETTING_ITEM_HEADER, KSCAMERA_PERFRAMESETTING_ITEM_HEADER, *PKSCAMERA_PERFRAMESETTING_ITEM_HEADER
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
req.alt-api: KSCAMERA_PERFRAMESETTING_ITEM_HEADER
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

# PKSCAMERA_PERFRAMESETTING_ITEM_HEADER structure



## -description
This structure contains the header information for a per-frame settings item.


## -syntax

````
typedef struct {
  ULONG     Size;
  ULONG     Type;
  ULONGLONG Flags;
} KSCAMERA_PERFRAMESETTING_ITEM_HEADER, *PKSCAMERA_PERFRAMESETTING_ITEM_HEADER;
````


## -struct-fields

### -field Size

The size of this header and the item payload that follows.

### -field Type

This contains a <a href="..\ksmedia\ne-ksmedia-kscamera_perframesetting_item_type.md">KSCAMERA_PERFRAMESETTING_ITEM_TYPE</a> structure.

### -field Flags

This is any one of the capability flags reported in the <a href="stream.kscamera_perframesetting_cap_item_header">KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER</a> Flags field.

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