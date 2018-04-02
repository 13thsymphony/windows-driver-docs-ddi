---
UID: NF:ntifs.SeSetSessionIdToken
title: SeSetSessionIdToken function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\sesetsessionidtoken.htm
old-project: ifsk
ms.assetid: 18c5ef8c-de72-4d2e-9bee-5b58bc5482c7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: SeSetSessionIdToken, SeSetSessionIdToken function [Installable File System Drivers], ifsk.sesetsessionidtoken, ntifs/SeSetSessionIdToken, seref_3af3660a-a2ba-4262-91bb-dff8533bcdcb.xml
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
-	SeSetSessionIdToken
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# SeSetSessionIdToken function
The <b>SeSetSessionIdToken</b> routine is reserved for system use.

## Syntax

```
NTKERNELAPI NTSTATUS SeSetSessionIdToken(
  PACCESS_TOKEN Token,
  ULONG         SessionId
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