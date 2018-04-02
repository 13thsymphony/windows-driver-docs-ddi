---
UID: NE:nfccx._NFC_CX_POLL_BAILOUT_CONFIG
title: "_NFC_CX_POLL_BAILOUT_CONFIG"
author: windows-driver-content
description: The NFC_CX_POLL_BAILOUT_CONFIG enumeration specifies poll mode bail out.
old-location: nfpdrivers\nfc_cx_poll_bailout_config.htm
old-project: nfpdrivers
ms.assetid: 1085EA0A-B688-4F77-80AF-E81CFE645CDF
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PNFC_CX_POLL_BAILOUT_CONFIG, NFC_CX_POLL_BAILOUT_CONFIG, NFC_CX_POLL_BAILOUT_CONFIG enumeration [Near-Field Proximity Drivers], NFC_CX_POLL_BAILOUT_CONFIG, *PNFC_CX_POLL_BAILOUT_CONFIG, NFC_CX_POLL_BAILOUT_CONFIG, *PNFC_CX_POLL_BAILOUT_CONFIG enumeration [Near-Field Proximity Drivers], NFC_CX_POLL_BAILOUT_DEFAULT, NFC_CX_POLL_BAILOUT_NFC_A, NFC_CX_POLL_BAILOUT_NFC_B, _NFC_CX_POLL_BAILOUT_CONFIG, nfccx/NFC_CX_POLL_BAILOUT_CONFIG, nfccx/NFC_CX_POLL_BAILOUT_DEFAULT, nfccx/NFC_CX_POLL_BAILOUT_NFC_A, nfccx/NFC_CX_POLL_BAILOUT_NFC_B, nfpdrivers.nfc_cx_poll_bailout_config"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
req.irql: Requires same
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	nfccx.h
api_name:
-	NFC_CX_POLL_BAILOUT_CONFIG, *PNFC_CX_POLL_BAILOUT_CONFIG
product:
- Windows
targetos: Windows
req.typenames: NFC_CX_POLL_BAILOUT_CONFIG, *PNFC_CX_POLL_BAILOUT_CONFIG
---

# _NFC_CX_POLL_BAILOUT_CONFIG Enumeration
The NFC_CX_POLL_BAILOUT_CONFIG enumeration specifies poll mode bail out.

## Syntax
```
typedef enum _NFC_CX_POLL_BAILOUT_CONFIG {
  NFC_CX_POLL_BAILOUT_DEFAULT  ,
  NFC_CX_POLL_BAILOUT_NFC_A    ,
  NFC_CX_POLL_BAILOUT_NFC_B
} NFC_CX_POLL_BAILOUT_CONFIG, *PNFC_CX_POLL_BAILOUT_CONFIG;
```

## Constants

<table>
            
                <tr>
                    <td>NFC_CX_POLL_BAILOUT_DEFAULT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>NFC_CX_POLL_BAILOUT_NFC_A</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>NFC_CX_POLL_BAILOUT_NFC_B</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | nfccx.h (include Ncidef.h) |

## See Also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>