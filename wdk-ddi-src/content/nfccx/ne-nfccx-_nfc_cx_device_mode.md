---
UID: NE:nfccx._NFC_CX_DEVICE_MODE
title: "_NFC_CX_DEVICE_MODE"
author: windows-driver-content
description: Specifies device mode flags.
old-location: nfpdrivers\nfc_cx_device_mode.htm
old-project: nfpdrivers
ms.assetid: B9996339-984D-4F6B-BFE9-2F536EC75924
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PNFC_CX_DEVICE_MODE, NFC_CX_DEVICE_MODE, NFC_CX_DEVICE_MODE enumeration [Near-Field Proximity Drivers], NFC_CX_DEVICE_MODE_DTA, NFC_CX_DEVICE_MODE_NCI, NFC_CX_DEVICE_MODE_RAW, _NFC_CX_DEVICE_MODE, nfccx/NFC_CX_DEVICE_MODE, nfccx/NFC_CX_DEVICE_MODE_DTA, nfccx/NFC_CX_DEVICE_MODE_NCI, nfccx/NFC_CX_DEVICE_MODE_RAW, nfpdrivers.nfc_cx_device_mode"
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
-	NFC_CX_DEVICE_MODE
product: Windows
targetos: Windows
req.typenames: NFC_CX_DEVICE_MODE, *PNFC_CX_DEVICE_MODE
---

# _NFC_CX_DEVICE_MODE Enumeration
Specifies device mode flags.

## Syntax
````
typedef enum _NFC_CX_DEVICE_MODE { 
  NFC_CX_DEVICE_MODE_NCI  = 0x00000000,
  NFC_CX_DEVICE_MODE_DTA  = 0x00000001,
  NFC_CX_DEVICE_MODE_RAW  = 0x00000002
} NFC_CX_DEVICE_MODE;
````

## Constants

<table>
            
                <tr>
                    <td>NFC_CX_DEVICE_MODE_NCI</td>
                    <td>Enable NCI mode.</td>
                </tr>
            
                <tr>
                    <td>NFC_CX_DEVICE_MODE_DTA</td>
                    <td>Enable DTA mode.</td>
                </tr>
            
                <tr>
                    <td>NFC_CX_DEVICE_MODE_RAW</td>
                    <td>Enable RAW mode.</td>
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