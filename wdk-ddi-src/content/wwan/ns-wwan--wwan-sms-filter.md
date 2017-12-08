---
UID: NS.wwan._WWAN_SMS_FILTER
title: WWAN_SMS_FILTER
author: windows-driver-content
description: The WWAN_SMS_FILTER structure represents the filter to apply to SMS messages on the MB device.
old-location: netvista\wwan_sms_filter.htm
old-project: netvista
ms.assetid: 798101da-51be-416d-ac56-2f55a21e8ea8
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WWAN_SMS_FILTER, WWAN_SMS_FILTER, *PWWAN_SMS_FILTER
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
req.alt-api: WWAN_SMS_FILTER
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

# WWAN_SMS_FILTER structure



## -description
<p>The WWAN_SMS_FILTER structure represents the filter to apply to SMS messages on the MB device.</p>


## -syntax

````
typedef struct _WWAN_SMS_FILTER {
  WWAN_SMS_FLAG Flag;
  ULONG         MessageIndex;
} WWAN_SMS_FILTER, *PWWAN_SMS_FILTER;
````


## -struct-fields
<dl>

### -field Flag

<dd>
<p>A value from the WWAN_SMS_FLAG enumeration that represents what filter to use to display SMS
     messages for.</p>
</dd>

### -field MessageIndex

<dd>
<p>A value between 1 and 
     <i>ulMaxMessageIndex</i> that is an index into the device's message store.
     </p>
<p>This value in this member is valid only if 
     <b>Flag</b> is set to 
     <b>WwanSmsFlagIndex</b>. The MB Service sets this member if 
     <b>Flag</b> is set to 
     <b>WwanSmsFlagIndex</b>. For all flags other than 
     <b>WwanSmsFlagIndex</b>, the MB Service sets this index to WWAN_MESSAGE_INDEX_NONE.</p>
</dd>
</dl>

## -remarks
<p>When 
    <b>Flag</b> is 
    <b>WwanSmsFlagIndex</b>, the filter identifies the SMS message specified by 
    <b>MessageIndex</b> .</p>

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
<a href="..\wwan\ne-wwan--wwan-sms-flag.md">WWAN_SMS_FLAG</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan--wwan-sms-read.md">WWAN_SMS_READ</a>
</dt>
<dt>
<a href="..\ndiswwan\ns-ndiswwan--ndis-wwan-sms-delete.md">NDIS_WWAN_SMS_DELETE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_FILTER structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
