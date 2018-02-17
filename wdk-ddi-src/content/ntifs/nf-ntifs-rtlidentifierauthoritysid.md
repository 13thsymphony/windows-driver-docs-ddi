---
UID: NF:ntifs.RtlIdentifierAuthoritySid
title: RtlIdentifierAuthoritySid function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\rtlidentifierauthoritysid.htm
old-project: ifsk
ms.assetid: cf81a653-19fd-45fc-ad38-3f701241fd80
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: RtlIdentifierAuthoritySid function [Installable File System Drivers], ifsk.rtlidentifierauthoritysid, rtlref_e4f051a9-6a6d-4008-b134-9a255b6764c0.xml, ntifs/RtlIdentifierAuthoritySid, RtlIdentifierAuthoritySid
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	RtlIdentifierAuthoritySid
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlIdentifierAuthoritySid function
The <b>RtlIdentifierAuthoritySid</b> routine is reserved for system use. See <a href="..\ntifs\nf-ntifs-rtlsubauthoritysid.md">RtlSubAuthoritySid</a> and <a href="..\ntifs\ns-ntifs-_sid.md">SID</a>.

## Syntax

````
  RtlIdentifierAuthoritySid(
    
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