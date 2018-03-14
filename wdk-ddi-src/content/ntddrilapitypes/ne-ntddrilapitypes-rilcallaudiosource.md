---
UID: NE:ntddrilapitypes.RILCALLAUDIOSOURCE
title: RILCALLAUDIOSOURCE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallaudiosource.htm
old-project: netvista
ms.assetid: ec6d45ba-3afe-44cb-a699-ef3b3b804b6b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILCALLAUDIOSOURCE, RILCALLAUDIOSOURCE enumeration [Network Drivers Starting with Windows Vista], RIL_CALLAUDIOSOURCE_MAX, RIL_CALLAUDIOSOURCE_PKT_APP, RIL_CALLAUDIOSOURCE_PKT_MODEM, netvista.rilcallaudiosource, ntddrilapitypes/RILCALLAUDIOSOURCE, ntddrilapitypes/RIL_CALLAUDIOSOURCE_MAX, ntddrilapitypes/RIL_CALLAUDIOSOURCE_PKT_APP, ntddrilapitypes/RIL_CALLAUDIOSOURCE_PKT_MODEM
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
-	RILCALLAUDIOSOURCE
product: Windows
targetos: Windows
req.typenames: RILCALLAUDIOSOURCE
---

# RILCALLAUDIOSOURCE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLAUDIOSOURCE { 
  RIL_CALLAUDIOSOURCE_PKT_MODEM,
  RIL_CALLAUDIOSOURCE_PKT_APP,
  RIL_CALLAUDIOSOURCE_MAX
} RILCALLAUDIOSOURCE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CALLAUDIOSOURCE_CIRCUIT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLAUDIOSOURCE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLAUDIOSOURCE_PKT_APP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLAUDIOSOURCE_PKT_MODEM</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |