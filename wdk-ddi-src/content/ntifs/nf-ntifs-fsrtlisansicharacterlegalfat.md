---
UID : NF:ntifs.FsRtlIsAnsiCharacterLegalFat
title : FsRtlIsAnsiCharacterLegalFat macro
author : windows-driver-content
description : The FsRtlIsAnsiCharacterLegalFat macro determines whether an ANSI character is legal for FAT file names.
old-location : ifsk\fsrtlisansicharacterlegalfat.htm
old-project : ifsk
ms.assetid : 4bbd50a8-1f1f-45d9-9b63-6c1576fe7b98
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ntifs/FsRtlIsAnsiCharacterLegalFat, fsrtlref_9d13203c-5fc4-4f4f-9372-09459f053bbc.xml, FsRtlIsAnsiCharacterLegalFat, ifsk.fsrtlisansicharacterlegalfat, FsRtlIsAnsiCharacterLegalFat function [Installable File System Drivers]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : ntifs.h
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# FsRtlIsAnsiCharacterLegalFat function
The <b>FsRtlIsAnsiCharacterLegalFat</b> macro determines whether an ANSI character is legal for FAT file names.

## Syntax

````
BOOLEAN FsRtlIsAnsiCharacterLegalFat(
   PSCHAR  *Character,
   BOOLEAN WildCardsPermissible
);
````

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
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegal.md">FsRtlIsAnsiCharacterLegal</a>

<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegalhpfs.md">FsRtlIsAnsiCharacterLegalHpfs</a>

<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegalntfs.md">FsRtlIsAnsiCharacterLegalNtfs</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsAnsiCharacterLegalFat function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>