---
UID: NS:wwan._WWAN_PIN_ACTION
title: "_WWAN_PIN_ACTION"
author: windows-driver-content
description: The WWAN_PIN_ACTION structure represents actions to perform with a Personal Identification Number (PIN).
old-location: netvista\wwan_pin_action.htm
old-project: netvista
ms.assetid: 4edd0bc1-cd50-460b-92e1-7b2440ae3861
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_PIN_ACTION, PWWAN_PIN_ACTION, PWWAN_PIN_ACTION structure pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_ACTION, WWAN_PIN_ACTION structure [Network Drivers Starting with Windows Vista], WwanRef_831c483c-8839-43a4-870d-f63ea3f78b61.xml, _WWAN_PIN_ACTION, netvista.wwan_pin_action, wwan/PWWAN_PIN_ACTION, wwan/WWAN_PIN_ACTION"
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
-	WWAN_PIN_ACTION
product:
- Windows
targetos: Windows
req.typenames: WWAN_PIN_ACTION, *PWWAN_PIN_ACTION
req.product: Windows 10 or later.
---

# _WWAN_PIN_ACTION structure
The WWAN_PIN_ACTION structure represents actions to perform with a Personal Identification Number
  (PIN).

## Syntax
```
typedef struct _WWAN_PIN_ACTION {
  WWAN_PIN_TYPE      PinType;
  WWAN_PIN_OPERATION PinOperation;
  WCHAR              Pin[WWAN_PIN_LEN];
  WCHAR              NewPin[WWAN_PIN_LEN];
} WWAN_PIN_ACTION, *PWWAN_PIN_ACTION;
```

## Members


`PinType`

The type of the PIN on which to perform the action.

`PinOperation`

The action to perform with the PIN.

`Pin`

A NULL-terminated string that represents the PIN value to perform the action with, or the PIN
     value required to enable/disable PIN settings. This member is a numeric value and applies for all values of 
     <b>PinOperation</b> .

`NewPin`

A NULL-terminated string that represents the new PIN value to set when 
     <b>PinOperation</b> is 
     <b>WwanPinOperationChange</b> or 
     <b>WwanPinOperationEnter</b>, for 
     <b>PinType</b><b>WwanPinTypePuk1</b> or 
     <b>WwanPinTypePuk2</b>. This member is a numeric value.

## Remarks
When 
    <b>PinType</b> is 
    <b>WwanPinTypePuk1</b> or 
    <b>WwanPinTypePuk2</b>, 
    <b>Pin</b> represents the corresponding PUK key.

When 
    <b>PinType</b> is 
    <b>WwanPinTypePuk1</b> or 
    <b>WwanPinTypePuk2, WwanPinOperationEnter</b> is the only supported value for 
    <b>PinOperation</b> .

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567922">NDIS_WWAN_SET_PIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571219">WWAN_PIN_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571221">WWAN_PIN_TYPE</a>