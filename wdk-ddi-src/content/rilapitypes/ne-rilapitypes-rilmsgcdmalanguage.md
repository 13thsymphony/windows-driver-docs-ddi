---
UID: NE:rilapitypes.RILMSGCDMALANGUAGE
title: RILMSGCDMALANGUAGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmalanguage_2.htm
old-project: netvista
ms.assetid: d1ad512e-10ba-4266-9688-2fc8e63bb4c4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_MSGCDMALANG_HEBREW, RIL_MSGCDMALANG_KOREAN, rilapitypes/RIL_MSGCDMALANG_CHINESE, rilapitypes/RIL_MSGCDMALANG_MAX, RIL_MSGCDMALANG_CHINESE, RIL_MSGCDMALANG_MAX, RIL_MSGCDMALANG_ENGLISH, rilapitypes/RILMSGCDMALANGUAGE, RIL_MSGCDMALANG_SPANISH, rilapitypes/RIL_MSGCDMALANG_ENGLISH, rilapitypes/RIL_MSGCDMALANG_JAPANESE, RILMSGCDMALANGUAGE, rilapitypes/RIL_MSGCDMALANG_FRENCH, RIL_MSGCDMALANG_JAPANESE, rilapitypes/RIL_MSGCDMALANG_HEBREW, RILMSGCDMALANGUAGE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_MSGCDMALANG_SPANISH, RIL_MSGCDMALANG_FRENCH, rilapitypes/RIL_MSGCDMALANG_KOREAN, netvista.rilmsgcdmalanguage_2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILMSGCDMALANGUAGE
product: Windows
targetos: Windows
req.typenames: RILMSGCDMALANGUAGE
req.product: Windows 10 or later.
---

# RILMSGCDMALANGUAGE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGCDMALANGUAGE { 
  RIL_MSGCDMALANG_ENGLISH,
  RIL_MSGCDMALANG_FRENCH,
  RIL_MSGCDMALANG_SPANISH,
  RIL_MSGCDMALANG_JAPANESE,
  RIL_MSGCDMALANG_KOREAN,
  RIL_MSGCDMALANG_CHINESE,
  RIL_MSGCDMALANG_HEBREW,
  RIL_MSGCDMALANG_MAX
} RILMSGCDMALANGUAGE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_MSGCDMALANG_CHINESE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCDMALANG_ENGLISH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCDMALANG_FRENCH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCDMALANG_HEBREW</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCDMALANG_JAPANESE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCDMALANG_KOREAN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCDMALANG_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCDMALANG_SPANISH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCDMALANG_UNKNOWN</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |