---
UID: NS.wwan._WWAN_USSD_EVENT
title: WWAN_USSD_EVENT
author: windows-driver-content
description: The WWAN_USSD_REQUEST structure describes an Unstructured Supplementary Service Data (USSD) event.
old-location: netvista\wwan_ussd_event.htm
old-project: netvista
ms.assetid: 5E90FB65-AF23-47C0-B0E9-2B6EF353D095
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WWAN_USSD_EVENT, WWAN_USSD_EVENT, *PWWAN_USSD_EVENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_USSD_EVENT
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
req.iface: 
req.product: Windows 10 or later.
---

# WWAN_USSD_EVENT structure



## -description
<p>The WWAN_USSD_REQUEST structure describes an Unstructured Supplementary Service Data (USSD) event.</p>


## -syntax

````
typedef struct _WWAN_USSD_EVENT {
  WWAN_USSD_EVENT_TYPE    EventType;
  WWAN_USSD_SESSION_STATE SessionState;
  WWAN_USSD_STRING        UssdString;
} WWAN_USSD_EVENT, *PWWAN_USSD_EVENT;
````


## -struct-fields
<dl>

### -field <b>EventType</b>

<dd>
<p>The type of USSD event.</p>
</dd>

### -field <b>SessionState</b>

<dd>
<p>The USSD string is the first message of a USSD session.</p>
</dd>

### -field <b>UssdString</b>

<dd>
<p>The USSD string that accompanies the event.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with  Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\wwan\ne-wwan--wwan-ussd-event-type.md">WWAN_USSD_EVENT_TYPE</a>
</dt>
<dt>
<a href="..\wwan\ne-wwan--wwan-ussd-session-state.md">WWAN_USSD_SESSION_STATE</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan--wwan-ussd-string.md">WWAN_USSD_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_USSD_EVENT structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
