---
UID: NE:ntddrilapitypes.RILRMCVTYPE
title: RILRMCVTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrmcvtype.htm
old-project: netvista
ms.assetid: 007c6b45-0bec-4fcf-984a-675aa5336993
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILRMCVTYPE, RILRMCVTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_RMCV_TYPE_BOOLEAN, RIL_RMCV_TYPE_DWORD, RIL_RMCV_TYPE_STRING, netvista.rilrmcvtype, ntddrilapitypes/RILRMCVTYPE, ntddrilapitypes/RIL_RMCV_TYPE_BOOLEAN, ntddrilapitypes/RIL_RMCV_TYPE_DWORD, ntddrilapitypes/RIL_RMCV_TYPE_STRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	RILRMCVTYPE
product:
- Windows
targetos: Windows
req.typenames: RILRMCVTYPE
---

# RILRMCVTYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILRMCVTYPE {
  RIL_RMCV_TYPE_NONE     ,
  RIL_RMCV_TYPE_BOOLEAN  ,
  RIL_RMCV_TYPE_DWORD    ,
  RIL_RMCV_TYPE_STRING
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_RMCV_TYPE_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RMCV_TYPE_BOOLEAN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RMCV_TYPE_DWORD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RMCV_TYPE_STRING</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |