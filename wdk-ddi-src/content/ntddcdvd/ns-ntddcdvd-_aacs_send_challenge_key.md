---
UID: NS.NTDDCDVD._AACS_SEND_CHALLENGE_KEY
title: _AACS_SEND_CHALLENGE_KEY
author: windows-driver-content
description: The AACS_SEND_CHALLENGE_KEY structure is defined as a challenge key that host software sends to an Advanced Access Content System (AACS) device.
old-location: storage\aacs_send_challenge_key.htm
old-project: storage
ms.assetid: 3985c396-7e85-46b6-8790-1ec45931a4ab
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _AACS_SEND_CHALLENGE_KEY, *PAACS_SEND_CHALLENGE_KEY, PAACS_SEND_CHALLENGE_KEY, AACS_SEND_CHALLENGE_KEY
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
req.alt-api: AACS_SEND_CHALLENGE_KEY
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

# _AACS_SEND_CHALLENGE_KEY structure



## -description
The AACS_SEND_CHALLENGE_KEY structure is defined as a challenge key that host software sends to an Advanced Access Content System (AACS) device.



## -syntax

````
typedef struct _AACS_SEND_CHALLENGE_KEY {
  DVD_SESSION_ID     SessionId;
  AACS_CHALLENGE_KEY ChallengeKey;
} AACS_SEND_CHALLENGE_KEY, *PAACS_SEND_CHALLENGE_KEY;
````


## -struct-fields

### -field SessionId

A value of type DVD_SESSION_ID that specifies an Authentication Grant Identifier (AGID).


### -field ChallengeKey

A structure of type <a href="storage.aacs_challenge_key">AACS_CHALLENGE_KEY</a> that specifies the challenge key to retrieve.


## -remarks
Host software send this challenge key to an AACS-compliant device with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_send_challenge_key.md">IOCTL_AACS_SEND_CHALLENGE_KEY</a> request.


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
<a href="storage.aacs_challenge_key">AACS_CHALLENGE_KEY</a>
</dt>
<dt>
<a href="storage.dvd_session_id">DVD_SESSION_ID</a>
</dt>
<dt>
<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_send_challenge_key.md">IOCTL_AACS_SEND_CHALLENGE_KEY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AACS_SEND_CHALLENGE_KEY structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

