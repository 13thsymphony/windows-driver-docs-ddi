---
UID: NS.wwan._WWAN_SET_SMS_CONFIGURATION
title: WWAN_SET_SMS_CONFIGURATION
author: windows-driver-content
description: The WWAN_SET_SMS_CONFIGURATION structure represents how MB devices support SMS configuration.
old-location: netvista\wwan_set_sms_configuration.htm
old-project: netvista
ms.assetid: c3739a08-f4ea-4cc5-8f62-7d4a5cd3ed43
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WWAN_SET_SMS_CONFIGURATION, WWAN_SET_SMS_CONFIGURATION, *PWWAN_SET_SMS_CONFIGURATION
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
req.alt-api: WWAN_SET_SMS_CONFIGURATION
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

# WWAN_SET_SMS_CONFIGURATION structure



## -description
<p>The WWAN_SET_SMS_CONFIGURATION structure represents how MB devices support SMS configuration.</p>


## -syntax

````
typedef struct _WWAN_SET_SMS_CONFIGURATION {
  CHAR            ScAddress[WWAN_SMS_ADDRESS_MAX_LEN];
  WWAN_SMS_FORMAT SmsFormat;
} WWAN_SET_SMS_CONFIGURATION, *PWWAN_SET_SMS_CONFIGURATION;
````


## -struct-fields
<dl>

### -field ScAddress

<dd>
<p>A NULL-terminated string with a maximum length of 15 digits that represents the Service Center
     (SC) address. This member is used by all text messages for sending and receiving. For PDU-style SMS
     messages, this information is used if it is not available in PDU data.
     </p>
<p>The number can be in any of the following formats:</p>
<ul>
<li>
<p>"+ &lt;International Country Code&gt; &lt;SMS Service Center Number&gt;\0"</p>
</li>
<li>
<p>"&lt;SMS Service Center Number&gt;\0"</p>
</li>
</ul>
<p>For 
     <i>set</i> requests, the MB Service can set this member to <b>NULL</b>. In this case, a <b>NULL</b> indicates the
     miniport driver does not need to update 
     <b>ScAddress</b> and should not update this member thereafter.</p>
</dd>

### -field SmsFormat

<dd>
<p>The SMS message format that should be used for the unsolicited indication of new SMS message
     arrivals. CDMA-based devices support only 
     <b>WwanSmsFormatCdma</b> format. The 
     <b>WwanSmsFormatCdma</b> format is does not apply to GSM-based devices.</p>
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
<p>Available in Windows 7 and later versions of Windows.</p>
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
<a href="..\wwan\ne-wwan--wwan-sms-format.md">WWAN_SMS_FORMAT</a>
</dt>
<dt>
<a href="..\ndiswwan\ns-ndiswwan--ndis-wwan-set-sms-configuration.md">
   NDIS_WWAN_SET_SMS_CONFIGURATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SET_SMS_CONFIGURATION structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
