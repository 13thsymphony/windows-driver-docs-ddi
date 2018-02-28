---
UID: NE:ntddrilapitypes.RILMSGDCSALPHABET
title: RILMSGDCSALPHABET
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcsalphabet.htm
old-project: netvista
ms.assetid: 21886c34-ca8d-4466-a3db-6841b2f59137
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMSGDCSALPHABET, RILMSGDCSALPHABET enumeration [Network Drivers Starting with Windows Vista], RIL_DCSALPHABET_8BIT, RIL_DCSALPHABET_MAX, RIL_DCSALPHABET_UCS2, netvista.rilmsgdcsalphabet, ntddrilapitypes/RILMSGDCSALPHABET, ntddrilapitypes/RIL_DCSALPHABET_8BIT, ntddrilapitypes/RIL_DCSALPHABET_MAX, ntddrilapitypes/RIL_DCSALPHABET_UCS2
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
-	RILMSGDCSALPHABET
product: Windows
targetos: Windows
req.typenames: RILMSGDCSALPHABET
---

# RILMSGDCSALPHABET Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGDCSALPHABET { 
  RIL_DCSALPHABET_8BIT,
  RIL_DCSALPHABET_UCS2,
  RIL_DCSALPHABET_MAX
} RILMSGDCSALPHABET;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_DCSALPHABET_8BIT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSALPHABET_DEFAULT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSALPHABET_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSALPHABET_UCS2</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |