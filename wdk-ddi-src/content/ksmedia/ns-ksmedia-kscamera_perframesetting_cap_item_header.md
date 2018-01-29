---
UID : NS:ksmedia.KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER
title : KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER
author : windows-driver-content
description : This structure contains the header information for a per-frame settings item.
old-location : stream\kscamera_perframesetting_cap_item_header.htm
old-project : stream
ms.assetid : 6E68CACB-4E0E-41E4-BAB6-0B7ECEFA92F6
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER, stream.kscamera_perframesetting_cap_item_header, ksmedia/PKSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER, *PKSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER, PKSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER structure pointer [Streaming Media Devices], KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER structure [Streaming Media Devices], ksmedia/KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER, PKSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PKSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER, KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER"
---

# KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER structure
This structure contains the header information for a per-frame settings item.

## Syntax
````
typedef struct {
  ULONG     Size;
  ULONG     Type;
  ULONGLONG Flags;
} KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER, *PKSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER;
````

## Members


`Flags`

This contains the supported capability flags.

`Size`

The size of this header and the item payload that follows.

`Type`

The <a href="..\ksmedia\ne-ksmedia-kscamera_perframesetting_item_type.md">KSCAMERA_PERFRAMESETTING_ITEM_TYPE</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h |