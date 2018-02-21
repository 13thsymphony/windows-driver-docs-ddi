---
UID: NE:wwan._WWAN_PIN_STATE
title: "_WWAN_PIN_STATE"
author: windows-driver-content
description: The WWAN_PIN_STATE enumeration describes whether the MB device or Subscriber Identity Module (SIM card) requires the user to enter a Personal Identification Number (PIN) to proceed to the next state.
old-location: netvista\wwan_pin_state.htm
old-project: netvista
ms.assetid: e538f920-bf9e-484b-acea-f979bb952299
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wwan/WwanPinStateEnter, *PWWAN_PIN_STATE, WwanPinStateEnter, WwanRef_6adb4dc1-c989-45b5-a27c-b553c9a5fdd0.xml, wwan/WWAN_PIN_STATE, WwanPinStateNone, netvista.wwan_pin_state, WwanPinStateMax, wwan/WwanPinStateMax, PWWAN_PIN_STATE, WWAN_PIN_STATE, wwan/PWWAN_PIN_STATE, wwan/WwanPinStateNone, PWWAN_PIN_STATE enumeration pointer [Network Drivers Starting with Windows Vista], _WWAN_PIN_STATE, WWAN_PIN_STATE enumeration [Network Drivers Starting with Windows Vista]
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
-	WWAN_PIN_STATE
product: Windows
targetos: Windows
req.typenames: WWAN_PIN_STATE, *PWWAN_PIN_STATE
req.product: Windows 10 or later.
---

# _WWAN_PIN_STATE Enumeration
The WWAN_PIN_STATE enumeration describes whether the MB device or Subscriber Identity Module (SIM
  card) requires the user to enter a Personal Identification Number (PIN) to proceed to the next
  state.

## Syntax
````
typedef enum _WWAN_PIN_STATE { 
  WwanPinStateNone   = 0,
  WwanPinStateEnter,
  WwanPinStateMax
} WWAN_PIN_STATE, *PWWAN_PIN_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>WwanPinStateEnter</td>
                    <td>The device requires the user to enter a PIN.</td>
                </tr>
            
                <tr>
                    <td>WwanPinStateMax</td>
                    <td>The total number of supported PIN states.</td>
                </tr>
            
                <tr>
                    <td>WwanPinStateNone</td>
                    <td>The device does not require a PIN.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_pin_info.md">WWAN_PIN_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PIN_STATE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>