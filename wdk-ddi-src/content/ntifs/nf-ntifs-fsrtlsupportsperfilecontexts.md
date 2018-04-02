---
UID: NF:ntifs.FsRtlSupportsPerFileContexts
title: FsRtlSupportsPerFileContexts macro
author: windows-driver-content
description: The FsRtlSupportsPerFileContexts macro checks if per file context information is supported by the file system that is associated with a specified FILE_OBJECT.
old-location: ifsk\fsrtlsupportsperfilecontexts.htm
old-project: ifsk
ms.assetid: 28f0e98f-1f7b-4dcf-8151-e13981634617
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlSupportsPerFileContexts, FsRtlSupportsPerFileContexts function [Installable File System Drivers], fsrtlref_98e99a7a-c80d-43d5-a0f6-3eea35a8d20a.xml, ifsk.fsrtlsupportsperfilecontexts, ntifs/FsRtlSupportsPerFileContexts
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntifs.h
api_name:
-	FsRtlSupportsPerFileContexts
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlSupportsPerFileContexts function
The <b>FsRtlSupportsPerFileContexts</b> macro checks if per file context information is supported by the file system that is associated with a specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>.

## Syntax

```
void FsRtlSupportsPerFileContexts(
   _fo
);
```

## Parameters

`_fo`

TBD


## Return Value

None

## Remarks

None

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating system.  |
| **Target Platform** | Desktop |
| **Header** | ntifs.h (include FltKernel.h, Ntifs.h) |
| **IRQL** | Any |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>



<a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>