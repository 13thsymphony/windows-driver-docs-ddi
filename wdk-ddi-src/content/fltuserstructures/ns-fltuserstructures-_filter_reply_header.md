---
UID: NS:fltuserstructures._FILTER_REPLY_HEADER
title: "_FILTER_REPLY_HEADER"
author: windows-driver-content
description: The FILTER_REPLY_HEADER structure contains message reply header information.
old-location: ifsk\filter_reply_header.htm
old-project: ifsk
ms.assetid: 2765ccb0-3389-4962-8a7d-8080cb3c8806
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFILTER_REPLY_HEADER, FILTER_REPLY_HEADER, FILTER_REPLY_HEADER structure [Installable File System Drivers], FltSystemStructures_93e9fad2-e89d-40af-8614-c09a51f07e7b.xml, PFILTER_REPLY_HEADER, PFILTER_REPLY_HEADER structure pointer [Installable File System Drivers], _FILTER_REPLY_HEADER, fltuserstructures/FILTER_REPLY_HEADER, fltuserstructures/PFILTER_REPLY_HEADER, ifsk.filter_reply_header"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltuserstructures.h
req.include-header: FltUser.h, Fltkernel.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltuserstructures.h
api_name:
-	FILTER_REPLY_HEADER
product:
- Windows
targetos: Windows
req.typenames: FILTER_REPLY_HEADER, *PFILTER_REPLY_HEADER
---

# _FILTER_REPLY_HEADER structure
The FILTER_REPLY_HEADER structure contains message reply header information.

## Syntax
```
typedef struct _FILTER_REPLY_HEADER {
  NTSTATUS  Status;
  ULONGLONG MessageId;
} FILTER_REPLY_HEADER, *PFILTER_REPLY_HEADER;
```

## Members


`Status`

Status value to be returned for the original message.

`MessageId`

Unique ID received in the <b>MessageId</b> field of the original message.

## Remarks
This structure is allocated by a user-mode application. It is a container for a reply that the application sends in response to a message received from a kernel-mode minifilter or minifilter instance.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | fltuserstructures.h (include FltUser.h, Fltkernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541621">FILTER_MESSAGE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a>