---
UID: NS.NTIFS._SID_AND_ATTRIBUTES
title: _SID_AND_ATTRIBUTES
author: windows-driver-content
description: The SID_AND_ATTRIBUTES structure represents a security identifier (SID) and its attributes. SIDs are used to uniquely identify users or groups.
old-location: ifsk\sid_and_attributes.htm
old-project: ifsk
ms.assetid: 37c299ab-16a6-4fa2-8ac9-55d75cc98f60
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SID_AND_ATTRIBUTES, PSID_AND_ATTRIBUTES, SID_AND_ATTRIBUTES, *PSID_AND_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SID_AND_ATTRIBUTES
req.alt-loc: ntifs.h
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

# _SID_AND_ATTRIBUTES structure



## -description
The SID_AND_ATTRIBUTES structure represents a security identifier (SID) and its attributes. SIDs are used to uniquely identify users or groups. 



## -syntax

````
typedef struct _SID_AND_ATTRIBUTES {
  PSID  Sid;
  ULONG Attributes;
} SID_AND_ATTRIBUTES, *PSID_AND_ATTRIBUTES;
````


## -struct-fields

### -field Sid

Pointer to a SID structure. 


### -field Attributes

Specifies attributes of the SID. This value contains up to 32 one-bit flags. Its meaning depends on the definition and use of the SID. 


## -remarks
A group is represented by a SID. SIDs have attributes that indicate whether they are currently enabled, disabled, or mandatory, and how they are used. A <b>SID_AND_ATTRIBUTES</b> structure can represent a SID whose attributes change frequently. For example, it is used to represent groups in the <a href="ifsk.token_groups">TOKEN_GROUPS</a> structure. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.ace">ACE</a>
</dt>
<dt>
<a href="ifsk.sefiltertoken">SeFilterToken</a>
</dt>
<dt>
<a href="ifsk.sid">SID</a>
</dt>
<dt>
<a href="ifsk.token_groups">TOKEN_GROUPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SID_AND_ATTRIBUTES structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

