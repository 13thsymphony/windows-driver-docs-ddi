---
UID: NE.wwan._WWAN_USSD_EVENT_TYPE
title: _WWAN_USSD_EVENT_TYPE
author: windows-driver-content
description: The WWAN_USSD_EVENT_TYPE enumeration lists the different types of Unstructured Supplementary Service Data (USSD) events.
old-location: netvista\wwan_ussd_event_type.htm
old-project: netvista
ms.assetid: CEBC8A75-03E9-4E2A-9092-2FA3005371FE
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WWAN_USSD_EVENT_TYPE, WWAN_USSD_EVENT_TYPE, *PWWAN_USSD_EVENT_TYPE
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
req.alt-api: WWAN_USSD_EVENT_TYPE
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

# _WWAN_USSD_EVENT_TYPE enumeration



## -description
The WWAN_USSD_EVENT_TYPE enumeration lists the different types of Unstructured Supplementary Service Data (USSD) events.



## -syntax

````
typedef enum _WWAN_USSD_EVENT_TYPE { 
  WwanUssdEventNoActionRequired       = 0,
  WwanUssdEventActionRequired         = 1,
  WwanUssdEventTerminated             = 2,
  WwanUssdEventOtherLocalClient       = 3,
  WwanUssdEventOperationNotSupported  = 4,
  WwanUssdEventNetworkTimeOut         = 5
} WWAN_USSD_EVENT_TYPE;
````


## -enum-fields

### -field WwanUssdEventNoActionRequired

Indicates no further action is required or information needed.


### -field WwanUssdEventActionRequired

Indicates the USSD session is still open and further information is needed, such as additional USSD strings.


### -field WwanUssdEventTerminated

Indicates the USSD session has been terminated.


### -field WwanUssdEventOtherLocalClient

Indicates an active USSD session already exists and that a new session cannot be established until the active session terminates. This includes sessions that are invisible to the MB stack such as a USSD session termination in the Subscriber Identity Module (SIM).


### -field WwanUssdEventOperationNotSupported

Indicates that the previous request is not supported by the miniport driver or MB device.


### -field WwanUssdEventNetworkTimeOut

Indicates that the USSD session was closed due to a session time-out either locally or by the network. The miniport driver or MB device is responsible for timing out an inactive USSD session after an implementation-specific time-out.


## -remarks
Network-initiated USSD events use <i>WwanUssdEventActionRequired</i> to indicate when further information is needed after an MB device initiated operation. <i>WwanUssdEventActionRequired</i> events also indicate that the session is still open. All other events indicate that the existing USSD session has been closed.

<i>WwanUssdEventNoActionRequired</i> and <i>WwanUssdEventActionRequired</i> are the only events that require a non-empty USSD string to accompany them with a string length from 1 to 160 bytes. All other events must set the USSD string length to 0 to indicate that the string is empty.

The value of the <a href="netvista.wwan_ussd_event">WWAN_USSD_EVENT</a><b>SessionState</b> member is ignored if no string is present.


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

## -see-also
<dl>
<dt>
<a href="netvista.wwan_ussd_event">WWAN_USSD_EVENT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_USSD_EVENT_TYPE enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

