---
UID: NS:hbapiwmi._MS_SMHBA_SASPHYSTATISTICS
title: "_MS_SMHBA_SASPHYSTATISTICS"
author: windows-driver-content
description: The MS_SMHBA_SASPHYSTATISTICS structure reports the traffic statistics for a SAS physical link.
old-location: storage\ms_smhba_sasphystatistics.htm
old-project: storage
ms.assetid: bb2ab242-9002-4760-86b2-1aaf203ff710
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MS_SMHBA_SASPHYSTATISTICS, PMS_SMHBA_SASPHYSTATISTICS, structs-Fibre_7059d482-c967-4f18-8c03-b113573cff2f.xml, MS_SMHBA_SASPHYSTATISTICS structure [Storage Devices], _MS_SMHBA_SASPHYSTATISTICS, hbapiwmi/MS_SMHBA_SASPHYSTATISTICS, *PMS_SMHBA_SASPHYSTATISTICS, hbapiwmi/PMS_SMHBA_SASPHYSTATISTICS, storage.ms_smhba_sasphystatistics, PMS_SMHBA_SASPHYSTATISTICS structure pointer [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
apiname:
-	MS_SMHBA_SASPHYSTATISTICS
product: Windows
targetos: Windows
req.typenames: MS_SMHBA_SASPHYSTATISTICS, *PMS_SMHBA_SASPHYSTATISTICS
---

# _MS_SMHBA_SASPHYSTATISTICS structure
The MS_SMHBA_SASPHYSTATISTICS structure reports the traffic statistics for a SAS physical link.

## Syntax
````
typedef struct _MS_SMHBA_SASPHYSTATISTICS {
  LONGLONG SecondsSinceLastReset;
  LONGLONG TxFrames;
  LONGLONG TxWords;
  LONGLONG RxFrames;
  LONGLONG RxWords;
  LONGLONG InvalidDwordCount;
  LONGLONG RunningDisparityErrorCount;
  LONGLONG LossofDwordSyncCount;
  LONGLONG PhyResetProblemCount;
} MS_SMHBA_SASPHYSTATISTICS, *PMS_SMHBA_SASPHYSTATISTICS;
````

## Members


`InvalidDwordCount`

The number of invalid DWORDs.

`LossofDwordSyncCount`

The loss of synchronization count.

`PhyResetProblemCount`

A count of the number of physical link reset problems.

`RunningDisparityErrorCount`

The number of disparity error counts.

`RxFrames`

The number of received SAS frames across all protocols and classes.

`RxWords`

The number of received SAS words across all protocols and classes.

`SecondsSinceLastReset`

The number of seconds since the statistics were last reset.

`TxFrames`

The number of transmitted SAS frames across all protocols and classes.

`TxWords`

The number of transmitted SAS words across all protocols and classes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |