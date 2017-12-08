---
UID: NS.WWAN._WWAN_PIN_DESC
title: _WWAN_PIN_DESC
author: windows-driver-content
description: The WWAN_PIN_DESC structure represents the description or current status for a Personal Identification Number (PIN).
old-location: netvista\wwan_pin_desc.htm
old-project: netvista
ms.assetid: a88f56eb-b527-4c7c-8f59-650dd10c671e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WWAN_PIN_DESC, WWAN_PIN_DESC, *PWWAN_PIN_DESC
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
req.alt-api: WWAN_PIN_DESC
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
req.product: Windows 10 or later.
---

# _WWAN_PIN_DESC structure



## -description
The WWAN_PIN_DESC structure represents the description or current status for a Personal
  Identification Number (PIN).


## -syntax

````
typedef struct _WWAN_PIN_DESC {
  WWAN_PIN_MODE   PinMode;
  WWAN_PIN_FORMAT PinFormat;
  ULONG           PinLengthMin;
  ULONG           PinLengthMax;
} WWAN_PIN_DESC, *PWWAN_PIN_DESC;
````


## -struct-fields

### -field PinMode

The current status of the PIN.

### -field PinFormat

The format of the PIN. This member is ignored if the 
     <b>PinMode</b> is 
     <b>WwanPinModeNotSupported</b>.

### -field PinLengthMin

The minimum number of characters in the PIN. Miniport drivers should not specify a value that is
     greater than WWAN_PIN_LEN (12). Miniport drivers should specify WWAN_PIN_LENGTH_UNKNOWN, if the PIN
     length is not available.

### -field PinLengthMax

The maximum number of characters in the PIN. Miniport drivers should not specify a value that is
     greater than WWAN_PIN_LEN (12). Miniport drivers should specify WWAN_PIN_LENGTH_UNKNOWN, if the PIN
     length is not available.

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
<a href="netvista.wwan_pin_mode">WWAN_PIN_MODE</a>
</dt>
<dt>
<a href="netvista.wwan_pin_format">WWAN_PIN_FORMAT</a>
</dt>
<dt>
<a href="netvista.wwan_pin_list">WWAN_PIN_LIST</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PIN_DESC structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
