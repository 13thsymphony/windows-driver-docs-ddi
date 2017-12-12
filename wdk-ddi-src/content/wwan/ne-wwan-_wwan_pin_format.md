---
UID: NE.wwan._WWAN_PIN_FORMAT
title: _WWAN_PIN_FORMAT
author: windows-driver-content
description: The WWAN_PIN_FORMAT enumeration lists the different Personal Identification Number (PIN) formats that are supported by the MB device.
old-location: netvista\wwan_pin_format.htm
old-project: netvista
ms.assetid: ccc3934c-fed4-4f9d-ae2a-d5e96bdb1e46
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WWAN_PIN_FORMAT, WWAN_PIN_FORMAT, *PWWAN_PIN_FORMAT
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
req.alt-api: WWAN_PIN_FORMAT
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

# _WWAN_PIN_FORMAT enumeration



## -description
The WWAN_PIN_FORMAT enumeration lists the different Personal Identification Number (PIN) formats that
  are supported by the MB device.



## -syntax

````
typedef enum _WWAN_PIN_FORMAT { 
  WwanPinFormatUnknown       = 0,
  WwanPinFormatNumeric,
  WwanPinFormatAlphaNumeric,
  WwanPinFormatMax
} WWAN_PIN_FORMAT, *PWWAN_PIN_FORMAT;
````


## -enum-fields

### -field WwanPinFormatUnknown

The format of PIN is not specified.


### -field WwanPinFormatNumeric

The format of the PIN allows only the numerical characters 0 through 9.


### -field WwanPinFormatAlphaNumeric

The format of the PIN allows alphanumeric characters a through z (lowercase), A through Z
     (uppercase), 0 through 9 (numeric), the asterisk symbol (*), and the pound symbol (#).


### -field WwanPinFormatMax

The total number of supported PIN formats.


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
<a href="netvista.wwan_pin_desc">WWAN_PIN_DESC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PIN_FORMAT enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

