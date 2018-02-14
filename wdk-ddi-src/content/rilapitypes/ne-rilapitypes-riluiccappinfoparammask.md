---
UID: NE:rilapitypes.RILUICCAPPINFOPARAMMASK
title: RILUICCAPPINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappinfoparammask_2.htm
old-project: netvista
ms.assetid: 17ca9b1c-aaf9-434e-be60-5698aa159b48
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILUICCAPPINFOPARAMMASK, RIL_PARAM_UICCAPPINFO_APPIDLENGTH, RILUICCAPPINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_UICCAPPINFO_APPNAME, RIL_PARAM_UICCAPPINFO_APPID, rilapitypes/RIL_PARAM_UICCAPPINFO_APPIDLENGTH, RILUICCAPPINFOPARAMMASK, RIL_PARAM_UICCAPPINFO_NUMPINS, rilapitypes/RIL_PARAM_UICCAPPINFO_NUMPINS, RIL_PARAM_UICCAPPINFO_PINREF, RIL_PARAM_UICCAPPINFO_APPNAME, rilapitypes/RIL_PARAM_UICCAPPINFO_APPID, RIL_PARAM_UICCAPPINFO_ALL, rilapitypes/RIL_PARAM_UICCAPPINFO_ALL, rilapitypes/RIL_PARAM_UICCAPPINFO_APPNAMELENGTH, RIL_PARAM_UICCAPPINFO_APPTYPE, RIL_PARAM_UICCAPPINFO_APPNAMELENGTH, rilapitypes/RIL_PARAM_UICCAPPINFO_PINREF, netvista.riluiccappinfoparammask_2, rilapitypes/RIL_PARAM_UICCAPPINFO_APPTYPE
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
-	RILUICCAPPINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCAPPINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILUICCAPPINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCAPPINFOPARAMMASK { 
  RIL_PARAM_UICCAPPINFO_APPTYPE,
  RIL_PARAM_UICCAPPINFO_APPIDLENGTH,
  RIL_PARAM_UICCAPPINFO_APPID,
  RIL_PARAM_UICCAPPINFO_APPNAMELENGTH,
  RIL_PARAM_UICCAPPINFO_APPNAME,
  RIL_PARAM_UICCAPPINFO_NUMPINS,
  RIL_PARAM_UICCAPPINFO_PINREF,
  RIL_PARAM_UICCAPPINFO_ALL
} RILUICCAPPINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_UICCAPPINFO_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UICCAPPINFO_APPID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UICCAPPINFO_APPIDLENGTH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UICCAPPINFO_APPNAME</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UICCAPPINFO_APPNAMELENGTH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UICCAPPINFO_APPTYPE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UICCAPPINFO_HUICCAPP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UICCAPPINFO_NUMPINS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UICCAPPINFO_PINREF</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |