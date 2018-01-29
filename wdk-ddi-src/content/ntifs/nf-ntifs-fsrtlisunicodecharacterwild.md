---
UID : NF:ntifs.FsRtlIsUnicodeCharacterWild
title : FsRtlIsUnicodeCharacterWild macro
author : windows-driver-content
description : The FsRtlIsUnicodeCharacterWild macro determines whether a Unicode character is a wildcard character.
old-location : ifsk\fsrtlisunicodecharacterwild.htm
old-project : ifsk
ms.assetid : 5e72aa2e-3aa6-49e5-b49f-339722060d5b
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FsRtlIsUnicodeCharacterWild, ntifs/FsRtlIsUnicodeCharacterWild, ifsk.fsrtlisunicodecharacterwild, FsRtlIsUnicodeCharacterWild function [Installable File System Drivers], fsrtlref_90047321-d510-4139-bfcf-d2f48c126834.xml
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


# FsRtlIsUnicodeCharacterWild function
The <b>FsRtlIsUnicodeCharacterWild</b> macro determines whether a Unicode character is a wildcard character.

## Syntax

````
BOOLEAN FsRtlIsUnicodeCharacterWild(
   PSCHAR *Character
);
````

## Parameters

`C`

TBD


## Return Value

None

## Remarks

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

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

<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterwild.md">FsRtlIsAnsiCharacterWild</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsUnicodeCharacterWild function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>