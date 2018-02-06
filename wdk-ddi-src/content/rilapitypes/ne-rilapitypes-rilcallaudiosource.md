---
UID: NE:rilapitypes.RILCALLAUDIOSOURCE
title: RILCALLAUDIOSOURCE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallaudiosource_2.htm
old-project: netvista
ms.assetid: 9da5508a-7397-4260-b5d8-16b0d624b98b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_CALLAUDIOSOURCE_PKT_MODEM, netvista.rilcallaudiosource_2, RILCALLAUDIOSOURCE, RIL_CALLAUDIOSOURCE_PKT_APP, rilapitypes/RIL_CALLAUDIOSOURCE_MAX, RILCALLAUDIOSOURCE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_CALLAUDIOSOURCE_PKT_MODEM, RIL_CALLAUDIOSOURCE_MAX, rilapitypes/RIL_CALLAUDIOSOURCE_PKT_APP, rilapitypes/RILCALLAUDIOSOURCE
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
-	RILCALLAUDIOSOURCE
product: Windows
targetos: Windows
req.typenames: RILCALLAUDIOSOURCE
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |