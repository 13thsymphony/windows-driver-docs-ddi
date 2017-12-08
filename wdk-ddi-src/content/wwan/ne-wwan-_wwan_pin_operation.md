---
UID: NE.wwan._WWAN_PIN_OPERATION
title: _WWAN_PIN_OPERATION
author: windows-driver-content
description: The WWAN_PIN_OPERATION enumeration lists the different Personal Identification Number (PIN) operations that are supported by the MB device.
old-location: netvista\wwan_pin_operation.htm
old-project: netvista
ms.assetid: 1b21b4b4-a35d-47c4-9cd6-e31e2dfbe59f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WWAN_PIN_OPERATION, WWAN_PIN_OPERATION, *PWWAN_PIN_OPERATION
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
req.alt-api: WWAN_PIN_OPERATION
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

# _WWAN_PIN_OPERATION enumeration



## -description
The WWAN_PIN_OPERATION enumeration lists the different Personal Identification Number (PIN)
  operations that are supported by the MB device.


## -syntax

````
typedef enum _WWAN_PIN_OPERATION { 
  WwanPinOperationEnter    = 0,
  WwanPinOperationEnable,
  WwanPinOperationDisable,
  WwanPinOperationChange,
  WwanPinOperationMax
} WWAN_PIN_OPERATION, *PWWAN_PIN_OPERATION;
````


## -enum-fields

### -field WwanPinOperationEnter

Enter the specified PIN into the device.

### -field WwanPinOperationEnable

Enable the specified PIN.

### -field WwanPinOperationDisable

Disable the specified PIN.

### -field WwanPinOperationChange

Change the specified PIN.

### -field WwanPinOperationMax

The total number of supported PIN operations.

## -remarks
If a PIN disable operation for a given PIN type is tried when that PIN type is locked, miniport
    drivers can either fail the request with WWAN_STATUS_PIN_REQUIRED or they can successfully complete the
    request. If miniport drivers complete the request successfully, the disable operation should also unlock
    the PIN.

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
<a href="netvista.wwan_pin_action">WWAN_PIN_ACTION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PIN_OPERATION enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
