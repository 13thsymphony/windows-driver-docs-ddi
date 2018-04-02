---
UID: NF:ntifs.ObQueryObjectAuditingByHandle
title: ObQueryObjectAuditingByHandle function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\obqueryobjectauditingbyhandle.htm
old-project: ifsk
ms.assetid: 7287b060-ab4c-48af-b5cd-67bae7bc1a73
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ObQueryObjectAuditingByHandle, ObQueryObjectAuditingByHandle function [Installable File System Drivers], ifsk.obqueryobjectauditingbyhandle, ntifs/ObQueryObjectAuditingByHandle, obref_1fb6339d-82a7-4c0f-bcaf-001886ebd898.xml
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
-	ObQueryObjectAuditingByHandle
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# ObQueryObjectAuditingByHandle function
The <b>ObQueryObjectAuditingByHandle</b> routine is reserved for system use.

## Syntax

```
NTKERNELAPI NTSTATUS ObQueryObjectAuditingByHandle(
  HANDLE   Handle,
  PBOOLEAN GenerateOnClose
);
```

## Parameters

`Handle`

TBD

`GenerateOnClose`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |