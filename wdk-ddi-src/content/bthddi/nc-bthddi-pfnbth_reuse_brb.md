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
ms.keywords: bltooth.bthreusebrb, BthReuseBrb callback function [Bluetooth Devices], BthReuseBrb, PFNBTH_REUSE_BRB, PFNBTH_REUSE_BRB, bthddi/BthReuseBrb, bth_funcs_118c4022-448d-4970-ba70-34dcbc488d13.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	bthddi.h
apiname:
-	BthReuseBrb
product: Windows
targetos: Windows
req.typenames: "*PMPEG2_TRANSPORT_STRIDE, MPEG2_TRANSPORT_STRIDE"
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
     <a href="..\bthddi\ne-bthddi-_brb_type.md">BRB_TYPE</a> enumeration to initialize the BRB
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

<a href="..\bthddi\ne-bthddi-_brb_type.md">BRB_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PFNBTH_REUSE_BRB callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>