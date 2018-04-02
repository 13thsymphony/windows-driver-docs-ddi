---
UID: NE:rilapitypes.RILCALLBARRINGSTATUSPARAMSSTATUS
title: RILCALLBARRINGSTATUSPARAMSSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallbarringstatusparamsstatus.htm
old-project: netvista
ms.assetid: aff61006-8bc4-4916-9718-a852516fc4d2
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILCALLBARRINGSTATUSPARAMSSTATUS, RILCALLBARRINGSTATUSPARAMSSTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_BARRINGSTATUS_ENABLED, RIL_BARRINGSTATUS_MAX, netvista.rilcallbarringstatusparamsstatus, ntddrilapitypes/RILCALLBARRINGSTATUSPARAMSSTATUS, ntddrilapitypes/RIL_BARRINGSTATUS_ENABLED, ntddrilapitypes/RIL_BARRINGSTATUS_MAX
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
-	RILCALLBARRINGSTATUSPARAMSSTATUS
product: Windows
targetos: Windows
req.typenames: RILCALLBARRINGSTATUSPARAMSSTATUS
req.product: Windows 10 or later.
---

# RILCALLBARRINGSTATUSPARAMSSTATUS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILCALLBARRINGSTATUSPARAMSSTATUS {
  RIL_BARRINGSTATUS_DISABLED  ,
  RIL_BARRINGSTATUS_ENABLED   ,
  RIL_BARRINGSTATUS_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_BARRINGSTATUS_DISABLED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_BARRINGSTATUS_ENABLED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_BARRINGSTATUS_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |