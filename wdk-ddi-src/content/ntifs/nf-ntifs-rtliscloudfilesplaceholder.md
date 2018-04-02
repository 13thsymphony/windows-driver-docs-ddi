---
UID: NF:ntifs.RtlIsCloudFilesPlaceholder
title: RtlIsCloudFilesPlaceholder function
author: windows-driver-content
description: The RtlIsCloudFilesPlaceholder routine determines if a file or a directory is a CloudFiles placeholder, based on the FileAttributes and ReparseTag values of the file.
old-location: ifsk\rtliscloudfilesplaceholder.htm
old-project: ifsk
ms.assetid: 9FF2EC69-0844-4FD7-A2BC-F16C42922212
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlIsCloudFilesPlaceholder, RtlIsCloudFilesPlaceholder routine [Installable File System Drivers], ifsk.rtliscloudfilesplaceholder, ntifs/RtlIsCloudFilesPlaceholder
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
req.dll: Ntdll.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntdll.dll
api_name:
-	RtlIsCloudFilesPlaceholder
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlIsCloudFilesPlaceholder function
The <b>RtlIsCloudFilesPlaceholder</b> routine determines if a file or a directory is a CloudFiles placeholder,
    based on the <b>FileAttributes</b> and <b>ReparseTag</b> values of the file. These values can be obtained by listing the directory containing the file or by directly querying <b>FileAttributeTagInfo</b> on the file.

## Syntax

```
NTSYSAPI BOOLEAN RtlIsCloudFilesPlaceholder(
  ULONG FileAttributes,
  ULONG ReparseTag
);
```

## Parameters

`FileAttributes`

Specifies the attributes of a file or directory.

`ReparseTag`

The ReparseTag or EaSize of a file or directory.


## Return Value

This function returns <b>TRUE</b> if the file or directory is a CloudFiles partial or full placeholder. It  returns <b>FALSE</b> if either the
        file or directory is not a CloudFiles placeholder.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10, version 1709.  |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |
| **DLL** | Ntdll.dll |

## See Also

<a href="https://msdn.microsoft.com/FB47F5BE-76B4-4A99-A15F-DE3E11D1DA2B">RtlIsPartialPlaceholder</a>