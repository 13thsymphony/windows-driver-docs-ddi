---
UID: NS.FLTUSERSTRUCTURES._FILTER_MESSAGE_HEADER
title: _FILTER_MESSAGE_HEADER
author: windows-driver-content
description: The FILTER_MESSAGE_HEADER structure contains message header information.
old-location: ifsk\filter_message_header.htm
old-project: ifsk
ms.assetid: 294e5475-3aca-4758-87ed-07892a910b4f
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _FILTER_MESSAGE_HEADER, *PFILTER_MESSAGE_HEADER, FILTER_MESSAGE_HEADER
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
req.alt-api: FILTER_MESSAGE_HEADER
req.alt-loc: fltuserstructures.h
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
---

# _FILTER_MESSAGE_HEADER structure



## -description
The FILTER_MESSAGE_HEADER structure contains message header information. 



## -syntax

````
typedef struct _FILTER_MESSAGE_HEADER {
  ULONG     ReplyLength;
  ULONGLONG MessageId;
} FILTER_MESSAGE_HEADER, *PFILTER_MESSAGE_HEADER;
````


## -struct-fields

### -field ReplyLength

On output from <a href="ifsk.filtergetmessage">FilterGetMessage</a>, this field receives the length, in bytes, of the expected reply, including the FILTER_REPLY_HEADER header. Set to zero if no reply is expected. 


### -field MessageId

On output from <a href="ifsk.filtergetmessage">FilterGetMessage</a>, this field receives the unique identifier (ID) for the message sent by the kernel-mode driver. If the application replies to the message, it must set this ID in the <b>MessageId</b> field of the FILTER_REPLY_HEADER header in the reply. 


## -remarks
To receive messages from a kernel-mode minifilter, a user-mode application typically defines a custom message structure. This structure typically consists of this header structure, followed by an application-defined structure to hold the actual message data. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fltuserstructures.h (include FltUser.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.filter_reply_header">FILTER_REPLY_HEADER</a>
</dt>
<dt>
<a href="ifsk.filtergetmessage">FilterGetMessage</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILTER_MESSAGE_HEADER structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

