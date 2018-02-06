---
UID: NE:rilapitypes.RILMSGSERVICEINFOPARAMMASK
title: RILMSGSERVICEINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgserviceinfoparammask_2.htm
old-project: netvista
ms.assetid: 2c5d29da-6577-4428-ac7b-1d3ff647086a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_PARAM_MSI_STORETOTAL, rilapitypes/RILMSGSERVICEINFOPARAMMASK, netvista.rilmsgserviceinfoparammask_2, RIL_PARAM_MSI_STORETOTAL, RILMSGSERVICEINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_MSI_STOREUSED, RIL_PARAM_MSI_ALL, rilapitypes/RIL_PARAM_MSI_ALL, RIL_PARAM_MSI_STOREUSED, RILMSGSERVICEINFOPARAMMASK
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
-	RILMSGSERVICEINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILMSGSERVICEINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILMSGSERVICEINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGSERVICEINFOPARAMMASK { 
  RIL_PARAM_MSI_STOREUSED,
  RIL_PARAM_MSI_STORETOTAL,
  RIL_PARAM_MSI_ALL
} RILMSGSERVICEINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_MSI_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MSI_MSGSUPPORT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MSI_STORETOTAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MSI_STOREUSED</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |