---
UID: NS.NTIFS._PUBLIC_OBJECT_BASIC_INFORMATION
title: _PUBLIC_OBJECT_BASIC_INFORMATION
author: windows-driver-content
description: The PUBLIC_OBJECT_BASIC_INFORMATION structure holds a subset of the full information that is available for an object.
old-location: ifsk\public_object_basic_information.htm
old-project: ifsk
ms.assetid: 2190f88e-6905-4e58-9523-2b6d4864c776
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _PUBLIC_OBJECT_BASIC_INFORMATION, PPUBLIC_OBJECT_BASIC_INFORMATION, *PPUBLIC_OBJECT_BASIC_INFORMATION, PUBLIC_OBJECT_BASIC_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Microsoft Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PUBLIC_OBJECT_BASIC_INFORMATION
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

# _PUBLIC_OBJECT_BASIC_INFORMATION structure



## -description
The PUBLIC_OBJECT_BASIC_INFORMATION structure holds a subset of the full information that is available for an object.



## -syntax

````
typedef struct _PUBLIC_OBJECT_BASIC_INFORMATION {
  ULONG       Attributes;
  ACCESS_MASK GrantedAccess;
  ULONG       HandleCount;
  ULONG       PointerCount;
  ULONG       Reserved[10];
} PUBLIC_OBJECT_BASIC_INFORMATION, *PPUBLIC_OBJECT_BASIC_INFORMATION;
````


## -struct-fields

### -field Attributes

Specifies the attributes of the object.


### -field GrantedAccess

Specifies a mask that represents the granted access to the object.


### -field HandleCount

Specifies the number of handles to the object.


### -field PointerCount

Specifies the number of pointers at an object.


### -field Reserved

Reserved for system use.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
This structure is available starting with Microsoft Windows 2000.

</td>
</tr>
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