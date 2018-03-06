---
UID: NS:ks.KSEVENT_TIME_MARK
title: KSEVENT_TIME_MARK
author: windows-driver-content
description: The KSEVENT_TIME_MARK structure is used in various events within the KSEVENTSETID_Clock event set.
old-location: stream\ksevent_time_mark.htm
old-project: stream
ms.assetid: c1e756a8-4850-4ddc-9bbf-97146a798554
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSEVENT_TIME_MARK, KSEVENT_TIME_MARK, KSEVENT_TIME_MARK structure [Streaming Media Devices], PKSEVENT_TIME_MARK, PKSEVENT_TIME_MARK structure pointer [Streaming Media Devices], ks-struct_66e60015-261c-4e6d-a58f-dab8d50cf4d6.xml, ks/KSEVENT_TIME_MARK, ks/PKSEVENT_TIME_MARK, stream.ksevent_time_mark"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	KSEVENT_TIME_MARK
product: Windows
targetos: Windows
req.typenames: KSEVENT_TIME_MARK, *PKSEVENT_TIME_MARK
---

# KSEVENT_TIME_MARK structure
The KSEVENT_TIME_MARK structure is used in various events within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561764">KSEVENTSETID_Clock</a> event set.

## Syntax
````
typedef struct {
  KSEVENTDATA EventData;
  LONGLONG    MarkTime;
} KSEVENT_TIME_MARK, *PKSEVENT_TIME_MARK;
````

## Members


`EventData`

A structure of type <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> that specifies the standard event structure.

`MarkTime`

Specifies the clock time when the event should be signaled.

## Remarks
The flags indicate the type of units for the interval. The interval can be specified in KSEVENT_DATA_MARKF_FILETIME units for these events, which are 100-nanosecond units.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-ksevent_time_interval.md">KSEVENT_TIME_INTERVAL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561764">KSEVENTSETID_Clock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSEVENT_TIME_MARK structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>