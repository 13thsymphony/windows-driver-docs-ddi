---
UID: NE:rilapitypes.RILMSGDCSPARAMMASK
title: RILMSGDCSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcsparammask_2.htm
old-project: netvista
ms.assetid: 58ec244c-ccd5-480d-8185-2c62273aeb1f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_MDCS_LANGUAGE, netvista.rilmsgdcsparammask_2, RIL_PARAM_MDCS_FLAGS, rilapitypes/RIL_PARAM_MDCS_FLAGS, RIL_PARAM_MDCS_MSGCLASS, rilapitypes/RILMSGDCSPARAMMASK, RIL_PARAM_MDCS_ALPHABET, RILMSGDCSPARAMMASK, rilapitypes/RIL_PARAM_MDCS_MSGCLASS, RIL_PARAM_MDCS_ALL, rilapitypes/RIL_PARAM_MDCS_LANGUAGE, rilapitypes/RIL_PARAM_MDCS_ALL, rilapitypes/RIL_PARAM_MDCS_INDICATION, rilapitypes/RIL_PARAM_MDCS_ALPHABET, RILMSGDCSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_MDCS_INDICATION
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
-	RILMSGDCSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILMSGDCSPARAMMASK
req.product: Windows 10 or later.
---

# RILMSGDCSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGDCSPARAMMASK { 
  RIL_PARAM_MDCS_FLAGS,
  RIL_PARAM_MDCS_MSGCLASS,
  RIL_PARAM_MDCS_ALPHABET,
  RIL_PARAM_MDCS_INDICATION,
  RIL_PARAM_MDCS_LANGUAGE,
  RIL_PARAM_MDCS_ALL
} RILMSGDCSPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_MDCS_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MDCS_ALPHABET</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MDCS_FLAGS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MDCS_INDICATION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MDCS_LANGUAGE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MDCS_MSGCLASS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MDCS_TYPE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |