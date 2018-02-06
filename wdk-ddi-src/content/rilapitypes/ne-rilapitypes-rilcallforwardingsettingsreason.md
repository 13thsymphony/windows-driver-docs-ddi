---
UID: NE:rilapitypes.RILCALLFORWARDINGSETTINGSREASON
title: RILCALLFORWARDINGSETTINGSREASON
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallforwardingsettingsreason_2.htm
old-project: netvista
ms.assetid: 765c34f7-c1c3-4579-b813-0c9845b3fabb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilcallforwardingsettingsreason_2, rilapitypes/RIL_FWDREASON_UNREACHABLE, RIL_FWDREASON_ALLCONDITIONAL, rilapitypes/RILCALLFORWARDINGSETTINGSREASON, RILCALLFORWARDINGSETTINGSREASON, RIL_FWDREASON_NOREPLY, rilapitypes/RIL_FWDREASON_MOBILEBUSY, RIL_FWDREASON_MOBILEBUSY, RIL_FWDREASON_UNREACHABLE, rilapitypes/RIL_FWDREASON_ALLFORWARDING, RIL_FWDREASON_MAX, rilapitypes/RIL_FWDREASON_ALLCONDITIONAL, rilapitypes/RIL_FWDREASON_MAX, rilapitypes/RIL_FWDREASON_NOREPLY, RIL_FWDREASON_ALLFORWARDING, RILCALLFORWARDINGSETTINGSREASON enumeration [Network Drivers Starting with Windows Vista]
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
-	RILCALLFORWARDINGSETTINGSREASON
product: Windows
targetos: Windows
req.typenames: RILCALLFORWARDINGSETTINGSREASON
req.product: Windows 10 or later.
---

# RILCALLFORWARDINGSETTINGSREASON Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLFORWARDINGSETTINGSREASON { 
  RIL_FWDREASON_MOBILEBUSY,
  RIL_FWDREASON_NOREPLY,
  RIL_FWDREASON_UNREACHABLE,
  RIL_FWDREASON_ALLFORWARDING,
  RIL_FWDREASON_ALLCONDITIONAL,
  RIL_FWDREASON_MAX
} RILCALLFORWARDINGSETTINGSREASON;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_FWDREASON_ALLCONDITIONAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_FWDREASON_ALLFORWARDING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_FWDREASON_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_FWDREASON_MOBILEBUSY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_FWDREASON_NOREPLY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_FWDREASON_UNCONDITIONAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_FWDREASON_UNREACHABLE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |