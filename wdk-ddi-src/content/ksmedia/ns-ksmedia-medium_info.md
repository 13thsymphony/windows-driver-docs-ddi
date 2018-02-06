---
UID: NS:ksmedia.MEDIUM_INFO
title: MEDIUM_INFO
author: windows-driver-content
description: The MEDIUM_INFO structure describes the media loaded into an external device.
old-location: stream\medium_info.htm
old-project: stream
ms.assetid: 1dd7415d-bfbc-4dea-bac9-bc5b8531a47f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.medium_info, ksmedia/PMEDIUM_INFO, PMEDIUM_INFO structure pointer [Streaming Media Devices], PMEDIUM_INFO, *PMEDIUM_INFO, vidcapstruct_f83c29e1-51a8-4784-a785-4e5dc9956634.xml, MEDIUM_INFO, MEDIUM_INFO structure [Streaming Media Devices], ksmedia/MEDIUM_INFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	MEDIUM_INFO
product: Windows
targetos: Windows
req.typenames: "*PMEDIUM_INFO, MEDIUM_INFO"
---

# MEDIUM_INFO structure
The MEDIUM_INFO structure describes the media loaded into an external device.

## Syntax
````
typedef struct {
  BOOL  MediaPresent;
  ULONG MediaType;
  BOOL  RecordInhibit;
} MEDIUM_INFO, *PMEDIUM_INFO;
````

## Members


`MediaPresent`

Specifies if media is present in the external device. <b>TRUE</b> if media is loaded, <b>FALSE</b> otherwise.

`MediaType`

Indicates the type of the media loaded in an external device.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ED_MEDIA_DVC

</td>
<td>
Digital video cassette. For example MiniDV

</td>
</tr>
<tr>
<td>
ED_MEDIA_VHS

</td>
<td>
VHS cassette

</td>
</tr>
<tr>
<td>
ED_MEDIA_HI8

</td>
<td>
Hi-8 cassette

</td>
</tr>
</table>

`RecordInhibit`

Specifies if recording is inhibited on the media. <b>TRUE</b> if recording onto the media is inhibited, <b>FALSE</b> otherwise.

## Remarks
Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |