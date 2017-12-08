---
UID: NS.NTDDCDVD._AACS_MEDIA_ID
title: _AACS_MEDIA_ID
author: windows-driver-content
description: The AACS_MEDIA_ID structure contains an Advanced Access Content System (AACS) media identifier and corresponding message authentication code (MAC).
old-location: storage\aacs_media_id.htm
old-project: storage
ms.assetid: 56be82fc-c438-4cd1-8fcc-1184699f03e6
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _AACS_MEDIA_ID, AACS_MEDIA_ID, *PAACS_MEDIA_ID
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
req.alt-api: AACS_MEDIA_ID
req.alt-loc: ntddcdvd.h
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
---

# _AACS_MEDIA_ID structure



## -description
The AACS_MEDIA_ID structure contains an Advanced Access Content System (AACS) media identifier and corresponding message authentication code (MAC).


## -syntax

````
typedef struct _AACS_MEDIA_ID {
  UCHAR MediaID[16];
  UCHAR MAC[16];
} AACS_MEDIA_ID, *PAACS_MEDIA_ID;
````


## -struct-fields

### -field MediaID

The media identifier.

### -field MAC

The message authentication code (MAC) that the client uses to verify that the MediaID is for the current AACS authentication sequence.

## -remarks
Clients retrieve the AACS certificate with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_media_id.md">IOCTL_AACS_READ_MEDIA_ID</a> request.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddcdvd.h (include Ntddcdvd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_media_id.md">IOCTL_AACS_READ_MEDIA_ID</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AACS_MEDIA_ID structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
