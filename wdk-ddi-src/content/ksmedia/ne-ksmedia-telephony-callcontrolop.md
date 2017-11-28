---
UID: NE.ksmedia.TELEPHONY_CALLCONTROLOP
title: TELEPHONY_CALLCONTROLOP
author: windows-driver-content
description: The TELEPHONY_CALLCONTROLOP enumeration defines constants that specify an operation to perform on a phone call.
old-location: audio\telephony_callcontrolop.htm
old-project: audio
ms.assetid: 5E6ECBCB-53AC-440B-92D9-21F5A06FCFAB
ms.author: windowsdriverdev
ms.date: 11/21/2017
ms.keywords: PKSIDEFAULTCLOCK, KSIDEFAULTCLOCK, *PKSIDEFAULTCLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10 Mobile
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TELEPHONY_CALLCONTROLOP
req.alt-loc: ksmedia.h
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
---

# TELEPHONY_CALLCONTROLOP enumeration



## -description
<p>The <b>TELEPHONY_CALLCONTROLOP</b> enumeration defines constants that specify an operation to perform on a phone call.</p>


## -syntax

````
typedef enum  { 
  TELEPHONY_CALLCONTROLOP_DISABLE  = 0,
  TELEPHONY_CALLCONTROLOP_ENABLE   = 1
} TELEPHONY_CALLCONTROLOP;
````


## -enum-fields
<dl>

### -field <a id="TELEPHONY_CALLCONTROLOP_DISABLE"></a><a id="telephony_callcontrolop_disable"></a><b>TELEPHONY_CALLCONTROLOP_DISABLE</b>

<dd>
<p>Disables a phone call.</p>
</dd>

### -field <a id="TELEPHONY_CALLCONTROLOP_ENABLE"></a><a id="telephony_callcontrolop_enable"></a><b>TELEPHONY_CALLCONTROLOP_ENABLE</b>

<dd>
<p>Enables a phone call.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum support</p>
</th>
<td width="70%">
<p>Windows 10 Mobile</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt169883">KSTELEPHONY_CALLCONTROL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20TELEPHONY_CALLCONTROLOP enumeration%20 RELEASE:%20(11/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
