---
UID: NE:rilapitypes.RILSYSTEMSELECTIONPREFSROAMINGMODE
title: RILSYSTEMSELECTIONPREFSROAMINGMODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemselectionprefsroamingmode_2.htm
old-project: netvista
ms.assetid: 7dbb25a5-7bcc-453d-854e-7796acbfd079
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_ROAMMODE_DOMESTIC, RIL_ROAMMODE_AUTOMATIC, rilapitypes/RIL_ROAMMODE_AUTOMATIC, netvista.rilsystemselectionprefsroamingmode_2, RILSYSTEMSELECTIONPREFSROAMINGMODE, rilapitypes/RILSYSTEMSELECTIONPREFSROAMINGMODE, RILSYSTEMSELECTIONPREFSROAMINGMODE enumeration [Network Drivers Starting with Windows Vista], RIL_ROAMMODE_DOMESTIC, rilapitypes/RIL_ROAMMODE_MAX, RIL_ROAMMODE_MAX
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
-	RILSYSTEMSELECTIONPREFSROAMINGMODE
product: Windows
targetos: Windows
req.typenames: RILSYSTEMSELECTIONPREFSROAMINGMODE
req.product: Windows 10 or later.
---

# RILSYSTEMSELECTIONPREFSROAMINGMODE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSYSTEMSELECTIONPREFSROAMINGMODE { 
  RIL_ROAMMODE_AUTOMATIC,
  RIL_ROAMMODE_DOMESTIC,
  RIL_ROAMMODE_MAX
} RILSYSTEMSELECTIONPREFSROAMINGMODE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_ROAMMODE_AUTOMATIC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ROAMMODE_DOMESTIC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ROAMMODE_HOMEONLY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ROAMMODE_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |