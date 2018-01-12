---
UID: NS:wwan._WWAN_PIN_INFO
title: _WWAN_PIN_INFO
author: windows-driver-content
description: The WWAN_PIN_INFO structure represents PIN type and PIN-entry state of Personal Identification Number (PIN) information required by the MB device.
old-location: netvista\wwan_pin_info.htm
old-project: netvista
ms.assetid: 0711645f-791b-4643-95c3-604ecce2a5ed
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _WWAN_PIN_INFO, *PWWAN_PIN_INFO, WWAN_PIN_INFO
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
req.alt-api: WWAN_PIN_INFO
req.alt-loc: wwan.h
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
req.typenames: *PWWAN_PIN_INFO, WWAN_PIN_INFO
req.product: Windows 10 or later.
---

# _WWAN_PIN_INFO structure



## -description
The WWAN_PIN_INFO structure represents PIN type and PIN-entry state of Personal Identification Number
  (PIN) information required by the MB device.



## -syntax

````
typedef struct _WWAN_PIN_INFO {
  WWAN_PIN_TYPE  PinType;
  WWAN_PIN_STATE PinState;
  ULONG          AttemptsRemaining;
} WWAN_PIN_INFO, *PWWAN_PIN_INFO;
````


## -struct-fields

### -field PinType

The type of PIN required to unlock the information stored on the device.


### -field PinState

The state of PIN-entry required to unlock the device.
     

This value indicates whether the device requires a PIN to be entered or not.


### -field AttemptsRemaining

The number of attempts that remain for any pin-related operations such as enter, enable, disable,
     and change.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wwan\ne-wwan-_wwan_pin_type.md">WWAN_PIN_TYPE</a>
</dt>
<dt>
<a href="..\wwan\ne-wwan-_wwan_pin_state.md">WWAN_PIN_STATE</a>
</dt>
<dt>
<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_pin_info.md">NDIS_WWAN_PIN_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PIN_INFO structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

