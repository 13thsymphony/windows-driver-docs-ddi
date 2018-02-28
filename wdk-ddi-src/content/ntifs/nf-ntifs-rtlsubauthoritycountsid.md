---
UID: NF:ntifs.RtlSubAuthorityCountSid
title: RtlSubAuthorityCountSid function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\rtlsubauthoritycountsid.htm
old-project: ifsk
ms.assetid: 11e825ad-3d8f-46cf-a08a-4027ff38ab90
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlSubAuthorityCountSid, RtlSubAuthorityCountSid function [Installable File System Drivers], ifsk.rtlsubauthoritycountsid, ntifs/RtlSubAuthorityCountSid, rtlref_a90cc5aa-161f-466b-975f-16ec42b70539.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	RtlSubAuthorityCountSid
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlSubAuthorityCountSid function
The <b>RtlSubAuthorityCountSid</b> routine is reserved for system use. See <a href="..\ntifs\nf-ntifs-rtlsubauthoritysid.md">RtlSubAuthoritySid</a> and <a href="..\ntifs\ns-ntifs-_sid.md">SID</a>.

## Syntax

````
  RtlSubAuthorityCountSid(
    
);
````

## Parameters

`Sid`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.exe |