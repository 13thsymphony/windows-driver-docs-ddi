---
UID: NS.KSMEDIA.PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM
title: PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM
author: windows-driver-content
description: This structure contains a custom item.
old-location: stream\kscamera_perframesetting_custom_item.htm
old-project: stream
ms.assetid: 7BB23F25-6E39-40B3-A158-5EE69370B1FD
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM, *PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM, KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM
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
req.alt-api: KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM
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

# PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM structure



## -description
This structure contains a custom item.


## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Reserved;
  GUID  Id;
} KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM, *PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM;
````


## -struct-fields

### -field Size

The size of this header and custom data that follows.

### -field Reserved

Reserved for future use.

### -field Id

A GUID that identifies the custom item.

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