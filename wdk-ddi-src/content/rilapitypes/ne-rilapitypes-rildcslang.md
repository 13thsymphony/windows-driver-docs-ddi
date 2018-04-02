---
UID: NE:rilapitypes.RILDCSLANG
title: RILDCSLANG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildcslang.htm
old-project: netvista
ms.assetid: bc39cb1a-d08a-40d7-a7c6-0342a90654dc
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILDCSLANG, RILDCSLANG enumeration [Network Drivers Starting with Windows Vista], RIL_DCSLANG_ALL, RIL_DCSLANG_ARABIC, RIL_DCSLANG_CZECH, RIL_DCSLANG_DANISH, RIL_DCSLANG_DUTCH, RIL_DCSLANG_ENGLISH, RIL_DCSLANG_FINNISH, RIL_DCSLANG_FRENCH, RIL_DCSLANG_GERMAN, RIL_DCSLANG_GREEK, RIL_DCSLANG_HEBREW, RIL_DCSLANG_HUNGARIAN, RIL_DCSLANG_ICELANDIC, RIL_DCSLANG_ITALIAN, RIL_DCSLANG_NORWEGIAN, RIL_DCSLANG_POLISH, RIL_DCSLANG_PORTUGUESE, RIL_DCSLANG_RUSSIAN, RIL_DCSLANG_SPANISH, RIL_DCSLANG_SWEDISH, RIL_DCSLANG_TURKISH, RIL_DCSLANG_UNKNOWN, netvista.rildcslang, ntddrilapitypes/RILDCSLANG, ntddrilapitypes/RIL_DCSLANG_ALL, ntddrilapitypes/RIL_DCSLANG_ARABIC, ntddrilapitypes/RIL_DCSLANG_CZECH, ntddrilapitypes/RIL_DCSLANG_DANISH, ntddrilapitypes/RIL_DCSLANG_DUTCH, ntddrilapitypes/RIL_DCSLANG_ENGLISH, ntddrilapitypes/RIL_DCSLANG_FINNISH, ntddrilapitypes/RIL_DCSLANG_FRENCH, ntddrilapitypes/RIL_DCSLANG_GERMAN, ntddrilapitypes/RIL_DCSLANG_GREEK, ntddrilapitypes/RIL_DCSLANG_HEBREW, ntddrilapitypes/RIL_DCSLANG_HUNGARIAN, ntddrilapitypes/RIL_DCSLANG_ICELANDIC, ntddrilapitypes/RIL_DCSLANG_ITALIAN, ntddrilapitypes/RIL_DCSLANG_NORWEGIAN, ntddrilapitypes/RIL_DCSLANG_POLISH, ntddrilapitypes/RIL_DCSLANG_PORTUGUESE, ntddrilapitypes/RIL_DCSLANG_RUSSIAN, ntddrilapitypes/RIL_DCSLANG_SPANISH, ntddrilapitypes/RIL_DCSLANG_SWEDISH, ntddrilapitypes/RIL_DCSLANG_TURKISH, ntddrilapitypes/RIL_DCSLANG_UNKNOWN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILDCSLANG
product: Windows
targetos: Windows
req.typenames: RILDCSLANG
req.product: Windows 10 or later.
---

# RILDCSLANG Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILDCSLANG {
  RIL_DCSLANG_None        ,
  RIL_DCSLANG_UNKNOWN     ,
  RIL_DCSLANG_GERMAN      ,
  RIL_DCSLANG_ENGLISH     ,
  RIL_DCSLANG_ITALIAN     ,
  RIL_DCSLANG_FRENCH      ,
  RIL_DCSLANG_SPANISH     ,
  RIL_DCSLANG_DUTCH       ,
  RIL_DCSLANG_SWEDISH     ,
  RIL_DCSLANG_DANISH      ,
  RIL_DCSLANG_PORTUGUESE  ,
  RIL_DCSLANG_FINNISH     ,
  RIL_DCSLANG_NORWEGIAN   ,
  RIL_DCSLANG_GREEK       ,
  RIL_DCSLANG_TURKISH     ,
  RIL_DCSLANG_HUNGARIAN   ,
  RIL_DCSLANG_POLISH      ,
  RIL_DCSLANG_CZECH       ,
  RIL_DCSLANG_HEBREW      ,
  RIL_DCSLANG_ARABIC      ,
  RIL_DCSLANG_RUSSIAN     ,
  RIL_DCSLANG_ICELANDIC   ,
  RIL_DCSLANG_ALL
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_DCSLANG_None</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_UNKNOWN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_GERMAN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_ENGLISH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_ITALIAN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_FRENCH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_SPANISH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_DUTCH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_SWEDISH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_DANISH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_PORTUGUESE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_FINNISH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_NORWEGIAN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_GREEK</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_TURKISH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_HUNGARIAN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_POLISH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_CZECH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_HEBREW</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_ARABIC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_RUSSIAN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_ICELANDIC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSLANG_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |