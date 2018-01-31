---
UID : NE:wwan._WWAN_REGISTER_MODE
title : "_WWAN_REGISTER_MODE"
author : windows-driver-content
description : The WWAN_REGISTER_MODE enumeration lists the different network selection modes which defines the way the device should select a network while registering.
old-location : netvista\wwan_register_mode.htm
old-project : netvista
ms.assetid : 608d041c-1034-49cf-b8da-cb3f7769ac55
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : WwanRegisterModeManual, wwan/PWWAN_REGISTER_MODE, wwan/WwanRegisterModeMax, netvista.wwan_register_mode, wwan/WwanRegisterModeAutomatic, PWWAN_REGISTER_MODE, wwan/WwanRegisterModeManual, wwan/WwanRegisterModeUnknown, WWAN_REGISTER_MODE, WWAN_REGISTER_MODE enumeration [Network Drivers Starting with Windows Vista], WwanRef_eac9611f-2097-43fc-96ea-ade56e77b7e7.xml, wwan/WWAN_REGISTER_MODE, WwanRegisterModeMax, PWWAN_REGISTER_MODE enumeration pointer [Network Drivers Starting with Windows Vista], _WWAN_REGISTER_MODE, *PWWAN_REGISTER_MODE, WwanRegisterModeAutomatic, WwanRegisterModeUnknown
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wwan.h
req.include-header : Wwan.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 7 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WWAN_REGISTER_MODE, *PWWAN_REGISTER_MODE
req.product : Windows 10 or later.
---

# _WWAN_REGISTER_MODE Enumeration
The WWAN_REGISTER_MODE enumeration lists the different network selection modes which defines the way
  the device should select a network while registering.

## Syntax
````
typedef enum _WWAN_REGISTER_MODE { 
  WwanRegisterModeUnknown    = 0,
  WwanRegisterModeAutomatic,
  WwanRegisterModeManual,
  WwanRegisterModeMax
} WWAN_REGISTER_MODE, *PWWAN_REGISTER_MODE;
````

## Constants

<table>

<tr>
<td>WwanRegisterModeAutomatic</td>
<td>Device automatically selects a network on which it should register.</td>
</tr>

<tr>
<td>WwanRegisterModeManual</td>
<td>Device registers to a pre-selected (manually selected) network.</td>
</tr>

<tr>
<td>WwanRegisterModeMax</td>
<td>The total number of supported registration modes.</td>
</tr>

<tr>
<td>WwanRegisterModeUnknown</td>
<td>It is not specified how the device registers with network providers.</td>
</tr>
</table>

## Remarks

<b>WwanRegisterModeAutomatic</b> and 
    <b>WwanRegisterModeManual</b> are the only acceptable values. Miniport drivers can return 
    <b>WwanRegisterModeManual</b> in cases where it is not able to get this value from device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_registration_state.md">WWAN_REGISTRATION_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_REGISTER_MODE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>