---
UID: NF:ntifs.SeQuerySessionIdToken
title: SeQuerySessionIdToken function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\sequerysessionidtoken.htm
old-project: ifsk
ms.assetid: 4b2e981d-1ad7-4f40-86d2-e6b210cec7d2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: SeQuerySessionIdToken, SeQuerySessionIdToken function [Installable File System Drivers], ifsk.sequerysessionidtoken, ntifs/SeQuerySessionIdToken, seref_9b30e13e-4132-4bc1-a2e1-7ccfb07b808e.xml
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
req.lib: 
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
-	SeQuerySessionIdToken
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# SeQuerySessionIdToken function
The <b>SeQuerySessionIdToken</b> routine is reserved for system use.

## Syntax

```
NTKERNELAPI NTSTATUS SeQuerySessionIdToken(
  PACCESS_TOKEN Token,
  PULONG        SessionId
);
```

## Parameters

`Token`

TBD

`SessionId`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |