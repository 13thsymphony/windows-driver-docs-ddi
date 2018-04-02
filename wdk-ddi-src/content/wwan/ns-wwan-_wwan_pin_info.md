---
UID: NS:wwan._WWAN_PIN_INFO
title: "_WWAN_PIN_INFO"
author: windows-driver-content
description: The WWAN_PIN_INFO structure represents PIN type and PIN-entry state of Personal Identification Number (PIN) information required by the MB device.
old-location: netvista\wwan_pin_info.htm
old-project: netvista
ms.assetid: 0711645f-791b-4643-95c3-604ecce2a5ed
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_PIN_INFO, PWWAN_PIN_INFO, PWWAN_PIN_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_INFO, WWAN_PIN_INFO structure [Network Drivers Starting with Windows Vista], WwanRef_aae7d248-25b1-465b-9314-66a16aca4993.xml, _WWAN_PIN_INFO, netvista.wwan_pin_info, wwan/PWWAN_PIN_INFO, wwan/WWAN_PIN_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	WWAN_PIN_INFO
product: Windows
targetos: Windows
req.typenames: WWAN_PIN_INFO, *PWWAN_PIN_INFO
req.product: Windows 10 or later.
---

# _WWAN_PIN_INFO structure
The WWAN_PIN_INFO structure represents PIN type and PIN-entry state of Personal Identification Number
  (PIN) information required by the MB device.

## Syntax
```
typedef struct _WWAN_PIN_INFO {
  WWAN_PIN_TYPE  PinType;
  WWAN_PIN_STATE PinState;
  ULONG          AttemptsRemaining;
} *PWWAN_PIN_INFO, WWAN_PIN_INFO;
```

## Members


`PinType`

The type of PIN required to unlock the information stored on the device.

`PinState`

The state of PIN-entry required to unlock the device.
     

This value indicates whether the device requires a PIN to be entered or not.

`AttemptsRemaining`

The number of attempts that remain for any pin-related operations such as enter, enable, disable,
     and change.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567911">NDIS_WWAN_PIN_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571220">WWAN_PIN_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571221">WWAN_PIN_TYPE</a>