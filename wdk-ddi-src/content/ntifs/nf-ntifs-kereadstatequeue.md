---
UID: NF:ntifs.KeReadStateQueue
title: KeReadStateQueue function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\kereadstatequeue.htm
old-project: ifsk
ms.assetid: 02bcc901-91f4-40fc-ab4b-de958e00f862
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: KeReadStateQueue, KeReadStateQueue function [Installable File System Drivers], ifsk.kereadstatequeue, keref_ae112949-4020-4501-8403-da1075d854c6.xml, ntifs/KeReadStateQueue
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
-	KeReadStateQueue
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# KeReadStateQueue function
The <b>KeReadStateQueue</b> routine is reserved for system use.

## Syntax

```
NTKERNELAPI LONG KeReadStateQueue(
  PRKQUEUE Queue
);
```

## Parameters

`Queue`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |