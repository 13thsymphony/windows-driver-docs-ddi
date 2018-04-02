---
UID: NS:ksmedia.tagTRANSPORTSTATUS
title: tagTRANSPORTSTATUS
author: windows-driver-content
description: The TRANSPORTSTATUS structure describes the current transport status.
old-location: stream\transportstatus.htm
old-project: stream
ms.assetid: 2896fd39-5c33-4c79-8adb-f6862b7b4314
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PTRANSPORTSTATUS, PTRANSPORTSTATUS, PTRANSPORTSTATUS structure pointer [Streaming Media Devices], TRANSPORTSTATUS, TRANSPORTSTATUS structure [Streaming Media Devices], ksmedia/PTRANSPORTSTATUS, ksmedia/TRANSPORTSTATUS, stream.transportstatus, tagTRANSPORTSTATUS, vidcapstruct_12a98ac2-58b9-47ce-ae09-30c8feeec2f0.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
api_name:
-	TRANSPORTSTATUS
product:
- Windows
targetos: Windows
req.typenames: TRANSPORTSTATUS, *PTRANSPORTSTATUS
---

# tagTRANSPORTSTATUS structure
The TRANSPORTSTATUS structure describes the current transport status.

## Syntax
```
typedef struct tagTRANSPORTSTATUS {
  LONG Mode;
  LONG LastError;
  LONG RecordInhibit;
  LONG ServoLock;
  LONG MediaPresent;
  LONG MediaLength;
  LONG MediaSize;
  LONG MediaTrackCount;
  LONG MediaTrackLength;
  LONG MediaTrackSide;
  LONG MediaType;
  LONG LinkMode;
  LONG NotifyOn;
} *PTRANSPORTSTATUS, TRANSPORTSTATUS;
```

## Members


`Mode`

Specifies the ED_MODE_Xxx.

`LastError`

Specifies the last error.

`RecordInhibit`

Specifies if recording is inhibited. <b>TRUE</b> if recording is prevented, <b>FALSE</b> otherwise.

`ServoLock`

Indicates the servo lock.

`MediaPresent`

Specifies if media is present.

`MediaLength`

Specifies the length of the media.

`MediaSize`

Specifies the size of the media.

`MediaTrackCount`

Indicates the media track count.

`MediaTrackLength`

Specifies the media track length.

`MediaTrackSide`

Indicates the media track size.

`MediaType`

Indicates the type of media.

`LinkMode`

Indicates linked mode. <b>TRUE</b> if linked, <b>FALSE</b> otherwise.

`NotifyOn`

Specifies event notification. <b>TRUE</b> enables event notification, <b>FALSE</b> disables event notification.

## Remarks
Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |