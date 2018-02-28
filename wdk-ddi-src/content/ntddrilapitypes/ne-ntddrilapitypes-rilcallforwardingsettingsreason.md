---
UID: NE:ntddrilapitypes.RILCALLFORWARDINGSETTINGSREASON
title: RILCALLFORWARDINGSETTINGSREASON
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallforwardingsettingsreason.htm
old-project: netvista
ms.assetid: d1c39f60-15fb-450d-b879-fb5d236fcf45
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLFORWARDINGSETTINGSREASON, RILCALLFORWARDINGSETTINGSREASON enumeration [Network Drivers Starting with Windows Vista], RIL_FWDREASON_ALLCONDITIONAL, RIL_FWDREASON_ALLFORWARDING, RIL_FWDREASON_MAX, RIL_FWDREASON_MOBILEBUSY, RIL_FWDREASON_NOREPLY, RIL_FWDREASON_UNREACHABLE, netvista.rilcallforwardingsettingsreason, ntddrilapitypes/RILCALLFORWARDINGSETTINGSREASON, ntddrilapitypes/RIL_FWDREASON_ALLCONDITIONAL, ntddrilapitypes/RIL_FWDREASON_ALLFORWARDING, ntddrilapitypes/RIL_FWDREASON_MAX, ntddrilapitypes/RIL_FWDREASON_MOBILEBUSY, ntddrilapitypes/RIL_FWDREASON_NOREPLY, ntddrilapitypes/RIL_FWDREASON_UNREACHABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	RILCALLFORWARDINGSETTINGSREASON
product: Windows
targetos: Windows
req.typenames: RILCALLFORWARDINGSETTINGSREASON
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
| **Header** | ntddrilapitypes.h |