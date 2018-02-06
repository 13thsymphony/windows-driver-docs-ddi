---
UID: NF:ntifs.MmGetMaximumFileSectionSize
title: MmGetMaximumFileSectionSize function
author: windows-driver-content
description: The MmGetMaximumFileSectionSize returns the maximum possible size of a file section for the current version of Windows.
old-location: ifsk\mmgetmaximumfilesectionsize.htm
old-project: ifsk
ms.assetid: 5B3E5B33-EFED-485A-A62A-7A54322408AC
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: MmGetMaximumFileSectionSize, ntifs/MmGetMaximumFileSectionSize, ifsk.mmgetmaximumfilesectionsize, MmGetMaximumFileSectionSize routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmGetMaximumFileSectionSize
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# MmGetMaximumFileSectionSize function
The <b>MmGetMaximumFileSectionSize</b> returns the maximum possible size of a file section for the current version of Windows.

## Syntax

````
ULONGLONG MmGetMaximumFileSectionSize(void);
````

## Parameters

This function has no parameters.

## Return Value

The maximum file section size supported by the current version of Windows.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |