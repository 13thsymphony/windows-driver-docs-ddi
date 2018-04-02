---
UID: NS:nfccx._NFC_CX_LLCP_CONFIG
title: "_NFC_CX_LLCP_CONFIG"
author: windows-driver-content
description: The NFC_CX_LLCP_CONFIG structure is an input parameter to NfcCxSetLlcpConfig.
old-location: nfpdrivers\nfc_cx_llcp_config.htm
old-project: nfpdrivers
ms.assetid: 84A1F957-FAAE-4C2D-9D49-486813A26950
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PNFC_CX_LLCP_CONFIG, NFC_CX_LLCP_CONFIG, NFC_CX_LLCP_CONFIG structure [Near-Field Proximity Drivers], PNFC_CX_LLCP_CONFIG, PNFC_CX_LLCP_CONFIG structure pointer [Near-Field Proximity Drivers], _NFC_CX_LLCP_CONFIG, nfccx/NFC_CX_LLCP_CONFIG, nfccx/PNFC_CX_LLCP_CONFIG, nfpdrivers.nfc_cx_llcp_config"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	nfccx.h
api_name:
-	NFC_CX_LLCP_CONFIG
product:
- Windows
targetos: Windows
req.typenames: NFC_CX_LLCP_CONFIG, *PNFC_CX_LLCP_CONFIG
---

# _NFC_CX_LLCP_CONFIG structure
The NFC_CX_LLCP_CONFIG structure is an input parameter to <a href="https://msdn.microsoft.com/8208F61E-DFD9-4AA8-B225-BEB35F80F621">NfcCxSetLlcpConfig.</a>

## Syntax
```
typedef struct _NFC_CX_LLCP_CONFIG {
  ULONG  Size;
  USHORT Miu;
  UCHAR  LinkTimeout;
  UCHAR  RecvWindowSize;
} *PNFC_CX_LLCP_CONFIG, NFC_CX_LLCP_CONFIG;
```

## Members


`Size`

Size of this structure in bytes.

`Miu`

Max information unit in bytes. Default is 1024.

`LinkTimeout`

LTO timeout in multiples of 10 milliseconds. Default is 100 (1 second).

`RecvWindowSize`

The receive window size per LLCP spec. Default value is 5.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | nfccx.h (include Ncidef.h) |

## See Also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>