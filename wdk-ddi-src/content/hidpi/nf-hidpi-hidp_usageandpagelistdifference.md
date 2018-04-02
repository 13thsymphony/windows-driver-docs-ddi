---
UID: NF:hidpi.HidP_UsageAndPageListDifference
title: HidP_UsageAndPageListDifference function
author: windows-driver-content
description: The HidP_UsageAndPageListDifference routine is not implemented.
old-location: hid\hidp_usageandpagelistdifference.htm
old-project: hid
ms.assetid: 80be9231-365d-4a38-8aa6-7da383bdcc40
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HidP_UsageAndPageListDifference, HidP_UsageAndPageListDifference function [Human Input Devices], hid.hidp_usageandpagelistdifference, hidfunc_0c86a540-d046-449f-a6ee-a122141fe6a3.xml, hidpi/HidP_UsageAndPageListDifference
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidpi.h
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
req.irql: TBD
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hidpi.h
api_name:
-	HidP_UsageAndPageListDifference
product:
- Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---


# HidP_UsageAndPageListDifference function
The <b>HidP_UsageAndPageListDifference</b> routine is not implemented.

## Syntax

```
NTSTATUS HidP_UsageAndPageListDifference(
  PUSAGE_AND_PAGE PreviousUsageList,
  PUSAGE_AND_PAGE CurrentUsageList,
  PUSAGE_AND_PAGE BreakUsageList,
  PUSAGE_AND_PAGE MakeUsageList,
  ULONG           UsageListLength
);
```

## Parameters

`PreviousUsageList`

TBD

`CurrentUsageList`

TBD

`BreakUsageList`

TBD

`MakeUsageList`

TBD

`UsageListLength`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | hidpi.h |
| **IRQL** | TBD |