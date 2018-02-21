---
UID: NE:wwan._WWAN_PIN_MODE
title: "_WWAN_PIN_MODE"
author: windows-driver-content
description: The WWAN_PIN_MODE enumeration lists the different states of a Personal Identification Number (PIN) type.
old-location: netvista\wwan_pin_mode.htm
old-project: netvista
ms.assetid: 55fa9dd4-370e-4f72-be40-4f14373cee27
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PWWAN_PIN_MODE, wwan/WwanPinModeEnabled, WwanRef_43194a1d-461a-4793-bb0b-40354466610c.xml, wwan/WwanPinModeDisabled, PWWAN_PIN_MODE enumeration pointer [Network Drivers Starting with Windows Vista], WwanPinModeDisabled, PWWAN_PIN_MODE, _WWAN_PIN_MODE, WWAN_PIN_MODE, WWAN_PIN_MODE enumeration [Network Drivers Starting with Windows Vista], wwan/WwanPinModeNotSupported, WwanPinModeMax, WwanPinModeNotSupported, netvista.wwan_pin_mode, wwan/WWAN_PIN_MODE, wwan/PWWAN_PIN_MODE, wwan/WwanPinModeMax, WwanPinModeEnabled"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_PIN_MODE
product: Windows
targetos: Windows
req.typenames: WWAN_PIN_MODE, *PWWAN_PIN_MODE
req.product: Windows 10 or later.
---

# _WWAN_PIN_MODE Enumeration
The WWAN_PIN_MODE enumeration lists the different states of a Personal Identification Number (PIN)
  type.

## Syntax
````
typedef enum _WWAN_PIN_MODE { 
  WwanPinModeNotSupported  = 0,
  WwanPinModeEnabled,
  WwanPinModeDisabled,
  WwanPinModeMax
} WWAN_PIN_MODE, *PWWAN_PIN_MODE;
````

## Constants

<table>
            
                <tr>
                    <td>WwanPinModeDisabled</td>
                    <td>The PIN type is supported though currently disabled.</td>
                </tr>
            
                <tr>
                    <td>WwanPinModeEnabled</td>
                    <td>The PIN type is supported and currently enabled.</td>
                </tr>
            
                <tr>
                    <td>WwanPinModeMax</td>
                    <td>The total number of supported PIN type states.</td>
                </tr>
            
                <tr>
                    <td>WwanPinModeNotSupported</td>
                    <td>The PIN type is not supported.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_pin_desc.md">WWAN_PIN_DESC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PIN_MODE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>