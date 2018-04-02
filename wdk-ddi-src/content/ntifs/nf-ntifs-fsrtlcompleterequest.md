---
UID: NF:ntifs.FsRtlCompleteRequest
title: FsRtlCompleteRequest macro
author: windows-driver-content
description: The FsRtlCompleteRequest macro completes an IRP with the specified status.
old-location: ifsk\fsrtlcompleterequest.htm
old-project: ifsk
ms.assetid: dd53d3c5-3a31-4ea9-9f16-0d1b9397f63e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlCompleteRequest, FsRtlCompleteRequest function [Installable File System Drivers], fsrtlref_ae47bec7-1534-4ace-a29b-d5b6a5da292c.xml, ifsk.fsrtlcompleterequest, ntifs/FsRtlCompleteRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlCompleteRequest
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlCompleteRequest function
The <b>FsRtlCompleteRequest</b> macro completes an IRP with the specified status.

## Syntax

```
void FsRtlCompleteRequest(
   IRP,
   STATUS
);
```

## Parameters

`IRP`

TBD

`STATUS`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntifs.h (include Ntifs.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548343">IoCompleteRequest</a>