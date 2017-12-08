---
UID: NS.WDM._LUID_AND_ATTRIBUTES
title: _LUID_AND_ATTRIBUTES
author: windows-driver-content
description: LUID_AND_ATTRIBUTES represents a locally unique identifier (LUID) and its attributes.
old-location: ifsk\luid_and_attributes.htm
old-project: ifsk
ms.assetid: d436cd60-d1ff-4a0c-b087-6aa50adfd7fc
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _LUID_AND_ATTRIBUTES, LUID_AND_ATTRIBUTES, *PLUID_AND_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: LUID_AND_ATTRIBUTES
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _LUID_AND_ATTRIBUTES structure



## -description
LUID_AND_ATTRIBUTES represents a locally unique identifier (LUID) and its attributes. 


## -syntax

````
typedef struct _LUID_AND_ATTRIBUTES {
  LUID  Luid;
  ULONG Attributes;
} LUID_AND_ATTRIBUTES, *PLUID_AND_ATTRIBUTES;
````


## -struct-fields

### -field Luid

An LUID value. 

### -field Attributes

Specifies attributes of the LUID. This value contains up to 32 one-bit flags. Its meaning depends on the definition and use of the LUID. 
The following attributes are defined for privileges: 
<table>
<tr>
<th>Attribute</th>
<th>Description</th>
</tr>
<tr>
<td>
SE_PRIVILEGE_ENABLED
</td>
<td>
The privilege is enabled. 
</td>
</tr>
<tr>
<td>
SE_PRIVILEGE_ENABLED_BY_DEFAULT
</td>
<td>
The privilege is enabled by default. 
</td>
</tr>
<tr>
<td>
SE_PRIVILEGE_USED_FOR_ACCESS
</td>
<td>
The privilege was used to gain access to an object or service. This flag is used to identify the relevant privileges in a set passed by a client application that may contain unnecessary privileges. 
</td>
</tr>
</table>
 

## -remarks
An LUID_AND_ATTRIBUTES structure can represent an LUID whose 
	 attributes change frequently, such as when it is used to represent 
	 privileges in the PRIVILEGE_SET structure. Privileges are represented by 
	 LUIDs and have attributes indicating whether they are currently enabled 
	 or disabled. 

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Ntddk.h, Ntifs.h, or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.luid">LUID</a>
</dt>
<dt>
<a href="ifsk.privilege_set">PRIVILEGE_SET</a>
</dt>
<dt>
<a href="ifsk.sefiltertoken">SeFilterToken</a>
</dt>
<dt>
<a href="ifsk.seprivilegecheck">SePrivilegeCheck</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20LUID_AND_ATTRIBUTES structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
