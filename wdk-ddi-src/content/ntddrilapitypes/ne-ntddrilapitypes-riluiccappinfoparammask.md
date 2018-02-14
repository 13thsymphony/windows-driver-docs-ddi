---
UID: NE:ntddrilapitypes.RILUICCAPPINFOPARAMMASK
title: RILUICCAPPINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappinfoparammask.htm
old-project: netvista
ms.assetid: 0e3bac55-6de7-4572-963f-dead9664cf1d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_UICCAPPINFO_APPIDLENGTH, RILUICCAPPINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RILUICCAPPINFOPARAMMASK, RIL_PARAM_UICCAPPINFO_NUMPINS, ntddrilapitypes/RIL_PARAM_UICCAPPINFO_APPIDLENGTH, netvista.riluiccappinfoparammask, RIL_PARAM_UICCAPPINFO_APPNAME, ntddrilapitypes/RIL_PARAM_UICCAPPINFO_NUMPINS, ntddrilapitypes/RIL_PARAM_UICCAPPINFO_APPNAMELENGTH, RIL_PARAM_UICCAPPINFO_ALL, ntddrilapitypes/RILUICCAPPINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_UICCAPPINFO_APPNAME, ntddrilapitypes/RIL_PARAM_UICCAPPINFO_ALL, ntddrilapitypes/RIL_PARAM_UICCAPPINFO_APPTYPE, RIL_PARAM_UICCAPPINFO_APPTYPE, RIL_PARAM_UICCAPPINFO_APPNAMELENGTH, ntddrilapitypes/RIL_PARAM_UICCAPPINFO_APPID, RIL_PARAM_UICCAPPINFO_APPID, RIL_PARAM_UICCAPPINFO_PINREF, ntddrilapitypes/RIL_PARAM_UICCAPPINFO_PINREF
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILUICCAPPINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCAPPINFOPARAMMASK
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
| **Header** | ntddrilapitypes.h |