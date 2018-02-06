---
UID: NE:rilapitypes.RILCALLBARRINGSTATUSPARAMSSTATUS
title: RILCALLBARRINGSTATUSPARAMSSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallbarringstatusparamsstatus_2.htm
old-project: netvista
ms.assetid: 0d7eff2c-7179-4517-a678-deb62315e53b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_BARRINGSTATUS_MAX, RIL_BARRINGSTATUS_MAX, RILCALLBARRINGSTATUSPARAMSSTATUS, RIL_BARRINGSTATUS_ENABLED, RILCALLBARRINGSTATUSPARAMSSTATUS enumeration [Network Drivers Starting with Windows Vista], netvista.rilcallbarringstatusparamsstatus_2, rilapitypes/RIL_BARRINGSTATUS_ENABLED, rilapitypes/RILCALLBARRINGSTATUSPARAMSSTATUS
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
-	RILCALLBARRINGSTATUSPARAMSSTATUS
product: Windows
targetos: Windows
req.typenames: RILCALLBARRINGSTATUSPARAMSSTATUS
req.product: Windows 10 or later.
---

# RILCALLBARRINGSTATUSPARAMSSTATUS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLBARRINGSTATUSPARAMSSTATUS { 
  RIL_BARRINGSTATUS_ENABLED,
  RIL_BARRINGSTATUS_MAX
} RILCALLBARRINGSTATUSPARAMSSTATUS;
````

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
| **Header** | rilapitypes.h |