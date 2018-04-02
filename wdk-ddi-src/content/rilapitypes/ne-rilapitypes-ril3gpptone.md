---
UID: NE:rilapitypes.RIL3GPPTONE
title: RIL3GPPTONE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril3gpptone.htm
old-project: netvista
ms.assetid: 3dd7c317-b77f-4cc1-8513-ed305418e76f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RIL3GPPTONE, RIL3GPPTONE enumeration [Network Drivers Starting with Windows Vista], RIL_3GPPTONE_AUTHENTICATIONFAILURE, RIL_3GPPTONE_BUSY, RIL_3GPPTONE_CALLDROPPED, RIL_3GPPTONE_CONGESTION, RIL_3GPPTONE_MAX, RIL_3GPPTONE_NUMBERUNOBTAINABLE, RIL_3GPPTONE_RINGBACK, netvista.ril3gpptone, ntddrilapitypes/RIL3GPPTONE, ntddrilapitypes/RIL_3GPPTONE_AUTHENTICATIONFAILURE, ntddrilapitypes/RIL_3GPPTONE_BUSY, ntddrilapitypes/RIL_3GPPTONE_CALLDROPPED, ntddrilapitypes/RIL_3GPPTONE_CONGESTION, ntddrilapitypes/RIL_3GPPTONE_MAX, ntddrilapitypes/RIL_3GPPTONE_NUMBERUNOBTAINABLE, ntddrilapitypes/RIL_3GPPTONE_RINGBACK
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
-	RIL3GPPTONE
product: Windows
targetos: Windows
req.typenames: RIL3GPPTONE
req.product: Windows 10 or later.
---

# RIL3GPPTONE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RIL3GPPTONE {
  RIL_3GPPTONE_TONEOFF                ,
  RIL_3GPPTONE_RINGBACK               ,
  RIL_3GPPTONE_BUSY                   ,
  RIL_3GPPTONE_CONGESTION             ,
  RIL_3GPPTONE_AUTHENTICATIONFAILURE  ,
  RIL_3GPPTONE_NUMBERUNOBTAINABLE     ,
  RIL_3GPPTONE_CALLDROPPED            ,
  RIL_3GPPTONE_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_3GPPTONE_TONEOFF</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_RINGBACK</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_BUSY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_CONGESTION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_AUTHENTICATIONFAILURE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_NUMBERUNOBTAINABLE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_CALLDROPPED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |