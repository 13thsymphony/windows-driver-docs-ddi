---
UID: NS.NTDDCDVD._AACS_SEND_CERTIFICATE
title: _AACS_SEND_CERTIFICATE
author: windows-driver-content
description: The AACS_SEND_CERTIFICATE structure is a wrapper for both an Advanced Access Content System (AACS) certificate and an Authentication Grant Identifier (AGID).
old-location: storage\aacs_send_certificate.htm
old-project: storage
ms.assetid: e0071ee1-7675-4029-b457-e7c26e642c31
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _AACS_SEND_CERTIFICATE, AACS_SEND_CERTIFICATE, *PAACS_SEND_CERTIFICATE
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
req.alt-api: AACS_SEND_CERTIFICATE
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

# _AACS_SEND_CERTIFICATE structure



## -description
The AACS_SEND_CERTIFICATE structure is a wrapper for both an Advanced Access Content System (AACS) certificate and an Authentication Grant Identifier (AGID).


## -syntax

````
typedef struct _AACS_SEND_CERTIFICATE {
  DVD_SESSION_ID   SessionId;
  AACS_CERTIFICATE Certificate;
} AACS_SEND_CERTIFICATE, *PAACS_SEND_CERTIFICATE;
````


## -struct-fields

### -field SessionId

A value of type DVD_SESSION_ID that specifies an AGID.

### -field Certificate

A structure of type <a href="storage.aacs_certificate">AACS_CERTIFICATE</a> that specifies the certificate to retrieve.

## -remarks
Clients send an Advanced Access Content System (AACS) certificate with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_send_certificate.md">IOCTL_AACS_SEND_CERTIFICATE</a> request. Clients retrieve an AACS certificate with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_get_certificate.md">IOCTL_AACS_GET_CERTIFICATE</a> request. 

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
<a href="storage.aacs_certificate">AACS_CERTIFICATE</a>
</dt>
<dt>
<a href="storage.dvd_session_id">DVD_SESSION_ID</a>
</dt>
<dt>
<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_get_certificate.md">IOCTL_AACS_GET_CERTIFICATE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AACS_SEND_CERTIFICATE structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
