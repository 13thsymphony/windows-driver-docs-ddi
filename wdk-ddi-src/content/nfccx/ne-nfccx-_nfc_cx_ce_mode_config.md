---
UID : NE:nfccx._NFC_CX_CE_MODE_CONFIG
title : "_NFC_CX_CE_MODE_CONFIG"
author : windows-driver-content
description : This enumeration specifies CE listening mode flags.
old-location : nfpdrivers\nfc_cx_ce_mode_config.htm
old-project : nfpdrivers
ms.assetid : 2C7071A4-B978-408C-9C98-67BC63F2BBCA
ms.author : windowsdriverdev
ms.date : 12/18/2017
ms.keywords : nfccx/NFC_CX_CE_DEFAULT, _NFC_CX_CE_MODE_CONFIG, NFC_CX_CE_NFC_A, nfccx/NFC_CX_CE_NFC_B, nfccx/NFC_CX_CE_NFC_F, NFC_CX_CE_MODE_CONFIG enumeration [Near-Field Proximity Drivers], NFC_CX_CE_MODE_CONFIG, NFC_CX_CE_DEFAULT, *PNFC_CX_CE_MODE_CONFIG, NFC_CX_CE_NFC_B, NFC_CX_CE_MODE_CONFIG, *PNFC_CX_CE_MODE_CONFIG enumeration [Near-Field Proximity Drivers], NFC_CX_CE_MODE_CONFIG, *PNFC_CX_CE_MODE_CONFIG, nfpdrivers.nfc_cx_ce_mode_config, nfccx/NFC_CX_CE_MODE_CONFIG, nfccx/NFC_CX_CE_NFC_A, NFC_CX_CE_NFC_F
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : nfccx.h
req.include-header : Ncidef.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : None supported
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Requires same
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NFC_CX_CE_MODE_CONFIG, *PNFC_CX_CE_MODE_CONFIG
---

# _NFC_CX_CE_MODE_CONFIG Enumeration
This enumeration specifies CE listening mode flags.

## Syntax
````
typedef enum _NFC_CX_CE_MODE_CONFIG { 
  NFC_CX_CE_NFC_A    = 0x01,
  NFC_CX_CE_NFC_B    = 0x02,
  NFC_CX_CE_NFC_F    = 0x04,
  NFC_CX_CE_DEFAULT  = NFC_CX_CE_NFC_A | NFC_CX_CE_NFC_B | NFC_CX_CE_NFC_F
} NFC_CX_CE_MODE_CONFIG, *PNFC_CX_CE_MODE_CONFIG;
````

## Constants

<table>

<tr>
<td>NFC_CX_CE_DEFAULT</td>
<td>Specifies NFC-A, NFC-B, and NFC-F listening mode.</td>
</tr>

<tr>
<td>NFC_CX_CE_NFC_A</td>
<td>Specifies NFC-A listening mode.</td>
</tr>

<tr>
<td>NFC_CX_CE_NFC_B</td>
<td>Specifies NFC-B listening mode.</td>
</tr>

<tr>
<td>NFC_CX_CE_NFC_F</td>
<td>Specifies NFC-F listening mode.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | nfccx.h (include Ncidef.h) |

## See Also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_CE_MODE_CONFIG enumeration%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>