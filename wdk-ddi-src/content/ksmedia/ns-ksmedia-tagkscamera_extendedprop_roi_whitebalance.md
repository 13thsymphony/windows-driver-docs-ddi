---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE
title: tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE
author: windows-driver-content
description: This structure contains the ROI info structure for white balance.
old-location: stream\kscamera_extendedprop_roi_whitebalance.htm
old-project: stream
ms.assetid: 16BDC61E-390C-4D79-A8D0-049404974733
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, ksmedia/PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE structure pointer [Streaming Media Devices], tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, *PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, stream.kscamera_extendedprop_roi_whitebalance, KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE structure [Streaming Media Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE
product: Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, *PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE
---

# tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE structure
This structure contains the ROI info structure for white balance.

## Syntax
````
typedef struct tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE {
  KSCAMERA_EXTENDEDPROP_ROI_INFO ROIInfo;
  ULONGLONG                      Reserved;
} KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, *PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE;
````

## Members


`Reserved`

Reserved for future use.

`ROIInfo`

See the <a href="..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_info.md">KSCAMERA_EXTENDEDPROP_ROI_INFO</a> structure for more information.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h |