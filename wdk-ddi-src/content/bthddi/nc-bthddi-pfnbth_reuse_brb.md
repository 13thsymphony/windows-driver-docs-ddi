---
UID: NC:bthddi.PFNBTH_REUSE_BRB
title: PFNBTH_REUSE_BRB
author: windows-driver-content
description: The BthReuseBrb function reinitializes a Bluetooth request block (BRB) to be reused.
old-location: bltooth\bthreusebrb.htm
old-project: bltooth
ms.assetid: cdf156a1-1556-441a-ae3d-9a49daf47990
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: BthReuseBrb, BthReuseBrb callback function [Bluetooth Devices], PFNBTH_REUSE_BRB, bltooth.bthreusebrb, bth_funcs_118c4022-448d-4970-ba70-34dcbc488d13.xml, bthddi/BthReuseBrb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	bthddi.h
api_name:
-	BthReuseBrb
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---


# PFNBTH_REUSE_BRB callback function
The 
  <i>BthReuseBrb</i> function reinitializes a Bluetooth request block (BRB) to be reused.

## Syntax

```
PFNBTH_REUSE_BRB PfnbthReuseBrb;

void PfnbthReuseBrb(
  PBRB pBrb,
  BRB_TYPE brbType
)
{...}
```

## Parameters

`pBrb`

Pointer to the BRB to reuse.

`brbType`

Specifies a value from the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536631">BRB_TYPE</a> enumeration to initialize the BRB
     with.


## Return Value

None.

## Remarks

Profile drivers obtain a pointer to the 
    <i>BthReuseBrb</i> function when they query the Bluetooth driver stack for an instance of the
    BTHDDI_PROFILE_DRIVER_INTERFACE driver interface. See 
    <a href="https://msdn.microsoft.com/56db29cd-26ab-4262-9b9f-40d46372ffe9">Querying for Bluetooth
    Interfaces</a> for more information about querying the Bluetooth driver stack.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later.  |
| **Target Platform** | Desktop |
| **Header** | bthddi.h (include Bthddi.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536631">BRB_TYPE</a>