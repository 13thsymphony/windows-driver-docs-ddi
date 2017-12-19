---
UID: NE.wwan._WWAN_REGISTER_MODE
title: _WWAN_REGISTER_MODE
author: windows-driver-content
description: The WWAN_REGISTER_MODE enumeration lists the different network selection modes which defines the way the device should select a network while registering.
old-location: netvista\wwan_register_mode.htm
old-project: NetVista
ms.assetid: 608d041c-1034-49cf-b8da-cb3f7769ac55
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WWAN_REGISTER_MODE, *PWWAN_REGISTER_MODE, WWAN_REGISTER_MODE, PWWAN_REGISTER_MODE
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
req.alt-api: WWAN_REGISTER_MODE
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

# _WWAN_REGISTER_MODE enumeration



## -description
The WWAN_REGISTER_MODE enumeration lists the different network selection modes which defines the way
  the device should select a network while registering.



## -syntax

````
typedef enum _WWAN_REGISTER_MODE { 
  WwanRegisterModeUnknown    = 0,
  WwanRegisterModeAutomatic,
  WwanRegisterModeManual,
  WwanRegisterModeMax
} WWAN_REGISTER_MODE, *PWWAN_REGISTER_MODE;
````


## -enum-fields

### -field WwanRegisterModeUnknown

It is not specified how the device registers with network providers.


### -field WwanRegisterModeAutomatic

Device automatically selects a network on which it should register.


### -field WwanRegisterModeManual

Device registers to a pre-selected (manually selected) network.


### -field WwanRegisterModeMax

The total number of supported registration modes.


## -remarks
<b>WwanRegisterModeAutomatic</b> and 
    <b>WwanRegisterModeManual</b> are the only acceptable values. Miniport drivers can return 
    <b>WwanRegisterModeManual</b> in cases where it is not able to get this value from device.


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
<a href="netvista.wwan_registration_state">WWAN_REGISTRATION_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20WWAN_REGISTER_MODE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

