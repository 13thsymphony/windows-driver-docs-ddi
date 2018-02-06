---
UID: NE:rilapitypes.RILSERVICESETTINGSSTATUS
title: RILSERVICESETTINGSSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilservicesettingsstatus_2.htm
old-project: netvista
ms.assetid: 4d193398-752f-4aef-8ae6-59c9afabd79a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSERVICESETTINGSSTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_SVCSTAT_MAX, rilapitypes/RILSERVICESETTINGSSTATUS, RIL_SVCSTAT_ENABLED, rilapitypes/RIL_SVCSTAT_ENABLED, RIL_SVCSTAT_DISABLED, RILSERVICESETTINGSSTATUS, netvista.rilservicesettingsstatus_2, rilapitypes/RIL_SVCSTAT_MAX, rilapitypes/RIL_SVCSTAT_DISABLED, rilapitypes/RIL_SVCSTAT_DEFAULT, RIL_SVCSTAT_DEFAULT
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
-	RILSERVICESETTINGSSTATUS
product: Windows
targetos: Windows
req.typenames: RILSERVICESETTINGSSTATUS
req.product: Windows 10 or later.
---

# RILSERVICESETTINGSSTATUS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSERVICESETTINGSSTATUS { 
  RIL_SVCSTAT_DISABLED,
  RIL_SVCSTAT_ENABLED,
  RIL_SVCSTAT_DEFAULT,
  RIL_SVCSTAT_MAX
} RILSERVICESETTINGSSTATUS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_SVCSTAT_DEFAULT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SVCSTAT_DISABLED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SVCSTAT_ENABLED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SVCSTAT_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SVCSTAT_UNKNOWN</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |