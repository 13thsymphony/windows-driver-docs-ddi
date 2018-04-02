---
UID: NF:ntifs.RtlIsPartialPlaceholder
title: RtlIsPartialPlaceholder function
author: windows-driver-content
description: The RtlIsPartialPlaceholder routine determines if a file or a directory is a CloudFiles placeholder, based on the FileAttributes and ReparseTag values of the file.
old-location: ifsk\rtlispartialplaceholder.htm
old-project: ifsk
ms.assetid: FB47F5BE-76B4-4A99-A15F-DE3E11D1DA2B
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlIsPartialPlaceholder, RtlIsPartialPlaceholder routine [Installable File System Drivers], ifsk.rtlispartialplaceholder, ntifs/RtlIsPartialPlaceholder
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
-	Ntifs.h
api_name:
-	RtlIsPartialPlaceholder
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlIsPartialPlaceholder function
The <b>RtlIsPartialPlaceholder</b> routine determines if a file or a directory is a CloudFiles placeholder,
    based on the <b>FileAttributes</b> and <b>ReparseTag</b> values of the file. These values can be obtained by listing the directory containing the file or by directly querying <b>FileAttributeTagInfo</b> on the file.

## Syntax

```
NTSYSAPI BOOLEAN RtlIsPartialPlaceholder(
  ULONG FileAttributes,
  ULONG ReparseTag
);
```

## Parameters

`FileAttributes`

Specifies the file attributes of a file or directory.

`ReparseTag`

The ReparseTag or EaSize of a file or directory.


## Return Value

This function returns <b>TRUE</b> if the file or directory is a partial placeholder. It  returns <b>FALSE</b> if either the
        file or directory is not a placeholder or is a full placeholder.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10, version 1709.  |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/A80C5714-525F-4E07-851D-2E203DD9387A">RtlIsPartialPlaceholderFileHandle</a>



<a href="https://msdn.microsoft.com/B84CC8C1-639D-45B4-A2A4-03BA2F1FF04B">RtlIsPartialPlaceholderFileInfo</a>