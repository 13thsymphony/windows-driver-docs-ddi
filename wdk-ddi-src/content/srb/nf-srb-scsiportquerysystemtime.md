---
UID: NF:srb.ScsiPortQuerySystemTime
title: ScsiPortQuerySystemTime function
author: windows-driver-content
description: The ScsiPortQuerySystemTime routine obtains the current system time.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportquerysystemtime.htm
old-project: storage
ms.assetid: 6f6afe6d-8f57-4c08-97ea-b327622a4e39
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: scsiprt_033d0cc3-e930-448b-a13e-b140829d2b7d.xml, storage.scsiportquerysystemtime, srb/ScsiPortQuerySystemTime, ScsiPortQuerySystemTime routine [Storage Devices], ScsiPortQuerySystemTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: 
req.target-type: Desktop
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
req.lib: Scsiport.lib
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Scsiport.lib
-	Scsiport.dll
apiname:
-	ScsiPortQuerySystemTime
product: Windows
targetos: Windows
req.typenames: "*PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG"
req.product: Windows 10 or later.
---


# ScsiPortQuerySystemTime function
The <b>ScsiPortQuerySystemTime</b> routine obtains the current system time.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID ScsiPortQuerySystemTime(
  _Out_ PLARGE_INTEGER CurrentTime
);
````

## Parameters

`CurrentTime`

Pointer to the current time, on return.


## Return Value

None

## Remarks

The system time returned in <i>CurrentTime</i> is the number of 100-nanosecond intervals that have elapsed since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h |
| **Library** | Scsiport.lib |
| **IRQL** | Any level |