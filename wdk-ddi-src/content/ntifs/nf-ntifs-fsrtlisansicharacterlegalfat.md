---
UID: NF:ntifs.FsRtlIsAnsiCharacterLegalFat
title: FsRtlIsAnsiCharacterLegalFat macro
author: windows-driver-content
description: The FsRtlIsAnsiCharacterLegalFat macro determines whether an ANSI character is legal for FAT file names.
old-location: ifsk\fsrtlisansicharacterlegalfat.htm
old-project: ifsk
ms.assetid: 4bbd50a8-1f1f-45d9-9b63-6c1576fe7b98
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlIsAnsiCharacterLegalFat, FsRtlIsAnsiCharacterLegalFat function [Installable File System Drivers], fsrtlref_9d13203c-5fc4-4f4f-9372-09459f053bbc.xml, ifsk.fsrtlisansicharacterlegalfat, ntifs/FsRtlIsAnsiCharacterLegalFat
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlIsAnsiCharacterLegalFat
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlIsAnsiCharacterLegalFat function
The <b>FsRtlIsAnsiCharacterLegalFat</b> macro determines whether an ANSI character is legal for FAT file names.

## Syntax

```
void FsRtlIsAnsiCharacterLegalFat(
   C,
   WILD_OK
);
```

## Parameters

`C`

TBD

`WILD_OK`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntifs.h (include Ntifs.h) |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546731">FsRtlIsAnsiCharacterLegal</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546761">FsRtlIsAnsiCharacterLegalHpfs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546768">FsRtlIsAnsiCharacterLegalNtfs</a>