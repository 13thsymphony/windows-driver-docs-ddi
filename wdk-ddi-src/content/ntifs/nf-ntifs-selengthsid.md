---
UID: NF:ntifs.SeLengthSid
title: SeLengthSid macro
author: windows-driver-content
description: Obsolete.
old-location: ifsk\selengthsid.htm
old-project: ifsk
ms.assetid: f6539ab6-709e-43e4-9e3f-595cf59c85c5
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.selengthsid, SeLengthSid, seref_d26b3191-e19a-4f62-b388-91d68976410f.xml, ntifs/SeLengthSid, SeLengthSid function [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.lib: ntifs.h
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
-	SeLengthSid
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# SeLengthSid function
This macro is exported to support existing driver binaries and is obsolete. Use <a href="..\ntifs\nf-ntifs-rtllengthsid.md">RtlLengthSid</a> instead.

## Syntax

````
  SeLengthSid(
    
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
| **Library** | ntifs.h |