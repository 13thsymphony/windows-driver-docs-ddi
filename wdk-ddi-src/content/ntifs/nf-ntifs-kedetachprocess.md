---
UID: NF:ntifs.KeDetachProcess
title: KeDetachProcess function
author: windows-driver-content
description: Obsolete.
old-location: ifsk\kedetachprocess.htm
old-project: ifsk
ms.assetid: 25cb0b53-f5b2-460a-bcab-56196f568d12
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: KeDetachProcess, KeDetachProcess function [Installable File System Drivers], ifsk.kedetachprocess, keref_0038ac90-7d97-45db-9a0d-028238af943d.xml, ntifs/KeDetachProcess
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
-	KeDetachProcess
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# KeDetachProcess function
The <b>KeDetachProcess</b> routine is exported to support existing driver binaries and is obsolete. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff549677">KeUnstackDetachProcess</a> instead.

## Syntax

```
NTKERNELAPI VOID KeDetachProcess(

);
```

## Parameters

This function has no parameters.

## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |