---
UID: NS.SCSI.PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
title: PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
author: windows-driver-content
description: A token, created as a representation of data (ROD), for an offload read data operation is returned in a RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure.
old-location: storage\receive_token_information_response_header.htm
old-project: storage
ms.assetid: 54168476-1C55-4343-858C-7FBA863D35D0
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, *PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
req.include-header: Scsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
req.alt-loc: scsi.h
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
req.product: Windows 10 or later.
---

# PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure



## -description
A token, created as a representation of data (ROD), for an offload read data operation is returned in a <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure.



## -syntax

````
typedef struct _RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER {
  UCHAR TokenDescriptorsLength[4];
  UCHAR TokenDescriptor[ANYSIZE_ARRAY];
} RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, *PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER;
````


## -struct-fields

### -field TokenDescriptorsLength

The length, in bytes, of the <b>TokenDescriptor</b> member.


### -field TokenDescriptor

The data containing a token created as the offload read ROD.


## -remarks
The <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure is included with a <a href="storage.receive_token_information_header">RECEIVE_TOKEN_INFORMATION_HEADER</a>structure  as a response to a POPULATE TOKEN command. The <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure follows the <b>SenseData</b> member of <b>RECEIVE_TOKEN_INFORMATION_HEADER</b>.

All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Scsi.h (include Scsi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.populate_token_header">POPULATE_TOKEN_HEADER</a>
</dt>
<dt>
<a href="storage.receive_token_information_header">RECEIVE_TOKEN_INFORMATION_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

