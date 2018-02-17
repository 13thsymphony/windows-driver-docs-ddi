---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_FOCUS
title: tagKSCAMERA_EXTENDEDPROP_ROI_FOCUS
author: windows-driver-content
description: This structure contains the ROI info structure for focus.
old-location: stream\kscamera_extendedprop_roi_focus.htm
old-project: stream
ms.assetid: 448A62D1-34D6-46EC-ADA4-9C9F832E2BDD
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_ROI_FOCUS, PKSCAMERA_EXTENDEDPROP_ROI_FOCUS structure pointer [Streaming Media Devices], tagKSCAMERA_EXTENDEDPROP_ROI_FOCUS, PKSCAMERA_EXTENDEDPROP_ROI_FOCUS, ksmedia/PKSCAMERA_EXTENDEDPROP_ROI_FOCUS, ksmedia/KSCAMERA_EXTENDEDPROP_ROI_FOCUS, KSCAMERA_EXTENDEDPROP_ROI_FOCUS, stream.kscamera_extendedprop_roi_focus, KSCAMERA_EXTENDEDPROP_ROI_FOCUS structure [Streaming Media Devices]"
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
-	KSCAMERA_EXTENDEDPROP_ROI_FOCUS
product: Windows
targetos: Windows
req.typenames: "*PKSCAMERA_EXTENDEDPROP_ROI_FOCUS, KSCAMERA_EXTENDEDPROP_ROI_FOCUS"
---

# tagKSCAMERA_EXTENDEDPROP_ROI_FOCUS structure
This structure contains the ROI info structure for focus.

## Syntax
````
typedef struct tagKSCAMERA_EXTENDEDPROP_ROI_FOCUS {
  KSCAMERA_EXTENDEDPROP_ROI_INFO ROIInfo;
  ULONGLONG                      Reserved;
} KSCAMERA_EXTENDEDPROP_ROI_FOCUS, *PKSCAMERA_EXTENDEDPROP_ROI_FOCUS;
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