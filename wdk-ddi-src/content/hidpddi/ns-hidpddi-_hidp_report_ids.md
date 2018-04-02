---
UID: NS:hidpddi._HIDP_REPORT_IDS
title: "_HIDP_REPORT_IDS"
author: windows-driver-content
description: Contains report ID information for a top-level collection.
old-location: hid\hidp_report_ids.htm
old-project: hid
ms.assetid: C88B77C3-01CB-4E8C-83A4-EB9AFB122327
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PHIDP_REPORT_IDS, HIDP_REPORT_IDS, HIDP_REPORT_IDS structure [Human Input Devices], PHIDP_REPORT_IDS, PHIDP_REPORT_IDS structure pointer [Human Input Devices], _HIDP_REPORT_IDS, hid.hidp_report_ids, hidpddi/HIDP_REPORT_IDS, hidpddi/PHIDP_REPORT_IDS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpddi.h
req.include-header: Hidpddi.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Hidpddi.h
api_name:
-	HIDP_REPORT_IDS
product:
- Windows
targetos: Windows
req.typenames: HIDP_REPORT_IDS, *PHIDP_REPORT_IDS
---

# _HIDP_REPORT_IDS structure
Contains report ID information for a top-level collection.

## Syntax
```
typedef struct _HIDP_REPORT_IDS {
  UCHAR  ReportID;
  UCHAR  CollectionNumber;
  USHORT InputLength;
  USHORT OutputLength;
  USHORT FeatureLength;
} *PHIDP_REPORT_IDS, HIDP_REPORT_IDS;
```

## Members


`ReportID`

The report ID of the top-level collection.

`CollectionNumber`

The index of the collection in the array of  <a href="https://msdn.microsoft.com/library/windows/hardware/mt740161">HIDP_COLLECTION_DESC</a> structure.

`InputLength`

The length of an input report of this report ID.

`OutputLength`

The length of an output report of this report ID. An input report, an output report, and a feature report can use the same report.

`FeatureLength`

The length of a feature report of this report ID.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidpddi.h (include Hidpddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt740164">HidP_GetCollectionDescription</a>