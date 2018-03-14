---
UID: NE:ntddrilapitypes.RILMSGDCSMSGCLASS
title: RILMSGDCSMSGCLASS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcsmsgclass.htm
old-project: netvista
ms.assetid: 3190aa21-201a-40d1-b894-dd393e413826
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILMSGDCSMSGCLASS, RILMSGDCSMSGCLASS enumeration [Network Drivers Starting with Windows Vista], RIL_DCSMSGCLASS_1, RIL_DCSMSGCLASS_2, RIL_DCSMSGCLASS_3, RIL_DCSMSGCLASS_MAX, netvista.rilmsgdcsmsgclass, ntddrilapitypes/RILMSGDCSMSGCLASS, ntddrilapitypes/RIL_DCSMSGCLASS_1, ntddrilapitypes/RIL_DCSMSGCLASS_2, ntddrilapitypes/RIL_DCSMSGCLASS_3, ntddrilapitypes/RIL_DCSMSGCLASS_MAX
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
-	RILMSGDCSMSGCLASS
product: Windows
targetos: Windows
req.typenames: RILMSGDCSMSGCLASS
---

# RILMSGDCSMSGCLASS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGDCSMSGCLASS { 
  RIL_DCSMSGCLASS_1,
  RIL_DCSMSGCLASS_2,
  RIL_DCSMSGCLASS_3,
  RIL_DCSMSGCLASS_MAX
} RILMSGDCSMSGCLASS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_DCSMSGCLASS_0</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSMSGCLASS_1</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSMSGCLASS_2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSMSGCLASS_3</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSMSGCLASS_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |