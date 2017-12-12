---
UID: NE.wwan._WWAN_USSD_SESSION_STATE
title: _WWAN_USSD_SESSION_STATE
author: windows-driver-content
description: The WWAN_USSD_SESSION_STATE enumeration lists the different types of USSD session states.
old-location: netvista\wwan_ussd_session_state.htm
old-project: netvista
ms.assetid: 5111A10F-F66F-4667-A77E-63691CCD282D
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WWAN_USSD_SESSION_STATE, *PWWAN_USSD_SESSION_STATE, WWAN_USSD_SESSION_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_USSD_SESSION_STATE
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

# _WWAN_USSD_SESSION_STATE enumeration



## -description
The WWAN_USSD_SESSION_STATE enumeration lists the different types of USSD session states.



## -syntax

````
typedef enum _WWAN_USSD_SESSION_STATE { 
  WwanUssdSessionStateNew       = 0,
  WwanUssdSessionStateExisting  = 1
} WWAN_USSD_SESSION_STATE;
````


## -enum-fields

### -field WwanUssdSessionStateNew

The USSD string is the first message of a USSD session.


### -field WwanUssdSessionStateExisting

The USSD string is not the first message of a USSD session.


## -remarks
Miniport drivers use the WWAN_USSD_SESSION_STATE enumeration to indicate whether a USSD string is the first message of a USSD session. Miniport drivers must use <i>WwanUssdSessionStateNew</i> for the first message of a network-initiated USSD session. Miniport drivers should use <i>WwanUssdSessionStateExisting</i> in all other cases.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with  Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wwan.h</dt>
</dl>
</td>
</tr>
</table>