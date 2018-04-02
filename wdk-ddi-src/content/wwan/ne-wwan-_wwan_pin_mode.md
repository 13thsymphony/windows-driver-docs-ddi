---
UID: NE:wwan._WWAN_PIN_MODE
title: "_WWAN_PIN_MODE"
author: windows-driver-content
description: The WWAN_PIN_MODE enumeration lists the different states of a Personal Identification Number (PIN) type.
old-location: netvista\wwan_pin_mode.htm
old-project: netvista
ms.assetid: 55fa9dd4-370e-4f72-be40-4f14373cee27
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_PIN_MODE, PWWAN_PIN_MODE, PWWAN_PIN_MODE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_MODE, WWAN_PIN_MODE enumeration [Network Drivers Starting with Windows Vista], WwanPinModeDisabled, WwanPinModeEnabled, WwanPinModeMax, WwanPinModeNotSupported, WwanRef_43194a1d-461a-4793-bb0b-40354466610c.xml, _WWAN_PIN_MODE, netvista.wwan_pin_mode, wwan/PWWAN_PIN_MODE, wwan/WWAN_PIN_MODE, wwan/WwanPinModeDisabled, wwan/WwanPinModeEnabled, wwan/WwanPinModeMax, wwan/WwanPinModeNotSupported"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	wwan.h
api_name:
-	WWAN_PIN_MODE
product:
- Windows
targetos: Windows
req.typenames: WWAN_PIN_MODE, *PWWAN_PIN_MODE
req.product: Windows 10 or later.
---

# _WWAN_PIN_MODE Enumeration
The WWAN_PIN_MODE enumeration lists the different states of a Personal Identification Number (PIN)
  type.

## Syntax
```
typedef enum _WWAN_PIN_MODE {
  WwanPinModeNotSupported  ,
  WwanPinModeEnabled       ,
  WwanPinModeDisabled      ,
  WwanPinModeMax
} *PWWAN_PIN_MODE, WWAN_PIN_MODE;
```

## Constants

<table>
            
                <tr>
                    <td>WwanPinModeNotSupported</td>
                    <td>The PIN type is not supported.</td>
                </tr>
            
                <tr>
                    <td>WwanPinModeEnabled</td>
                    <td>The PIN type is supported and currently enabled.</td>
                </tr>
            
                <tr>
                    <td>WwanPinModeDisabled</td>
                    <td>The PIN type is supported though currently disabled.</td>
                </tr>
            
                <tr>
                    <td>WwanPinModeMax</td>
                    <td>The total number of supported PIN type states.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff571214">WWAN_PIN_DESC</a>