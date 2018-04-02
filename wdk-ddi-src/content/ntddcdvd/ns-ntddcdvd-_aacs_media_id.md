---
UID: NS:ntddcdvd._AACS_MEDIA_ID
title: "_AACS_MEDIA_ID"
author: windows-driver-content
description: The AACS_MEDIA_ID structure contains an Advanced Access Content System (AACS) media identifier and corresponding message authentication code (MAC).
old-location: storage\aacs_media_id.htm
old-project: storage
ms.assetid: 56be82fc-c438-4cd1-8fcc-1184699f03e6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PAACS_MEDIA_ID, AACS_MEDIA_ID, AACS_MEDIA_ID structure [Storage Devices], PAACS_MEDIA_ID, PAACS_MEDIA_ID structure pointer [Storage Devices], _AACS_MEDIA_ID, ntddcdvd/AACS_MEDIA_ID, ntddcdvd/PAACS_MEDIA_ID, storage.aacs_media_id, structs-DVD_413a14c6-75e0-444f-b325-8dfeb9c0c074.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	ntddcdvd.h
api_name:
-	AACS_MEDIA_ID
product:
- Windows
targetos: Windows
req.typenames: AACS_MEDIA_ID, *PAACS_MEDIA_ID
---

# _AACS_MEDIA_ID structure
The AACS_MEDIA_ID structure contains an Advanced Access Content System (AACS) media identifier and corresponding message authentication code (MAC).

## Syntax
```
typedef struct _AACS_MEDIA_ID {
  UCHAR MediaID[16];
  UCHAR MAC[16];
} AACS_MEDIA_ID, *PAACS_MEDIA_ID;
```

## Members


`MediaID`

The media identifier.

`MAC`

The message authentication code (MAC) that the client uses to verify that the MediaID is for the current AACS authentication sequence.

## Remarks
Clients retrieve the AACS certificate with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559272">IOCTL_AACS_READ_MEDIA_ID</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559272">IOCTL_AACS_READ_MEDIA_ID</a>