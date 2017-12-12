---
UID: NE.avc._tagAvcCommandType
title: _tagAvcCommandType
author: windows-driver-content
description: The AvcCommandType enumeration type is used to indicate the type of command issued by a subunit driver to its AV/C subunit through AVC_FUNCTION_COMMAND or AVC_FUNCTION_GET_REQUEST function codes.
old-location: stream\avccommandtype.htm
old-project: stream
ms.assetid: 18bf43bd-3499-4494-839b-9bc07de83644
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _tagAvcCommandType, AvcCommandType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AvcCommandType
req.alt-loc: avc.h
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

# _tagAvcCommandType enumeration



## -description
The AvcCommandType enumeration type is used to indicate the type of command issued by a subunit driver to its AV/C subunit through <b>AVC_FUNCTION_COMMAND</b> or <b>AVC_FUNCTION_GET_REQUEST</b> function codes.



## -syntax

````
typedef enum _tagAvcCommandType { 
  AVC_CTYPE_CONTROL   = 0x00,
  AVC_CTYPE_STATUS    = 0x01,
  AVC_CTYPE_SPEC_INQ  = 0x02,
  AVC_CTYPE_NOTIFY    = 0x03,
  AVC_CTYPE_GEN_INQ   = 0x04
} AvcCommandType;
````


## -enum-fields

### -field AVC_CTYPE_CONTROL

Specifies a control type of command.


### -field AVC_CTYPE_STATUS

Specifies a status type of command.


### -field AVC_CTYPE_SPEC_INQ

Specifies a specific-inquiry type of command. This permits a controller to inform targets that a specific set of operands must by furnished along with the opcode when issuing a command.


### -field AVC_CTYPE_NOTIFY

Specifies a notify type of command.


### -field AVC_CTYPE_GEN_INQ

Specifies a general inquiry command type. This permits a controller to query a target to find out if it supports a specific opcode without needing to pass any specific operands.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Avc.h (include Avc.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554150">AVC_FUNCTION_COMMAND</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554163">AVC_FUNCTION_GET_REQUEST</a>
</dt>
<dt>
<a href="stream.avc_function">AVC_FUNCTION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AvcCommandType enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

