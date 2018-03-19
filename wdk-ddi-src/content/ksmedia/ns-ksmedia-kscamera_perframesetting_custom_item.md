---
UID: NS:ksmedia.KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM
title: KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM
author: windows-driver-content
description: This structure contains a custom item.
old-location: stream\kscamera_perframesetting_custom_item.htm
old-project: stream
ms.assetid: 7BB23F25-6E39-40B3-A158-5EE69370B1FD
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM, KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM, KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM structure [Streaming Media Devices], PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM, PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM, ksmedia/PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM, stream.kscamera_perframesetting_custom_item"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ksmedia.h
api_name:
-	KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM
product: Windows
targetos: Windows
req.typenames: KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM, *PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM
---

# KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM structure
This structure contains a custom item.

## Syntax
````
typedef struct {
  ULONG Size;
  ULONG Reserved;
  GUID  Id;
} KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM, *PKSCAMERA_PERFRAMESETTING_CUSTOM_ITEM;
````

## Members


`Size`

The size of this header and custom data that follows.

`Reserved`

Reserved for future use.

`Id`

A GUID that identifies the custom item.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h |