---
UID: NS.storport._STOR_UNIT_ATTRIBUTES
title: STOR_UNIT_ATTRIBUTES
author: windows-driver-content
description: The STOR_UNIT_ATTRIBUTES structure contains bitfields indicating attribute support for a storage device unit.
old-location: storage\stor_unit_attributes.htm
old-project: storage
ms.assetid: 9677C044-354B-4575-B2EC-187D1B4E8C61
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: STOR_UNIT_ATTRIBUTES, STOR_UNIT_ATTRIBUTES, *PSTOR_UNIT_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STOR_UNIT_ATTRIBUTES
req.alt-loc: Storport.h
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

# STOR_UNIT_ATTRIBUTES structure



## -description
<p>The <b>STOR_UNIT_ATTRIBUTES</b> structure contains bitfields indicating attribute support for a storage device unit.</p>


## -syntax

````
typedef struct _STOR_UNIT_ATTRIBUTES {
  ULONG DeviceAttentionSupported  :1;
  ULONG AsyncNotificationSupported  :1;
  ULONG D3ColdNotSupported  :1;
  ULONG Reserved  :29;
} STOR_UNIT_ATTRIBUTES, *PSTOR_UNIT_ATTRIBUTES;
````


## -struct-fields
<dl>

### -field <b>DeviceAttentionSupported</b>

<dd>
<p>Set to 1 if device attention is supported for the unit. Otherwise, set to 0.</p>
</dd>

### -field <b>AsyncNotificationSupported</b>

<dd>
<p>Set to 1 if the device supports asynchronous notifications. Otherwise, set to 0.</p>
</dd>

### -field <b>D3ColdNotSupported</b>

<dd>
<p>Set to 1 if the D3 Cold power state is NOT supported. Otherwise, set to 0.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved bits. Must be set to 0.</p>
</dd>
</dl>

## -remarks
<p>The unit attributes are registered with Storport  using this structure as a parameter to the <a href="..\storport\nf-storport-storportsetunitattributes.md">StorPortSetUnitAttributes</a> routine.</p>

<p>If the miniport driver supports asynchronous notifications, the <b>AsyncNotificationSupported</b> field set to 1, it will send notifications to the Storport driver using the <a href="..\storport\nf-storport-storportasyncnotificationdetected.md">StorPortAsyncNotificationDetected</a> routine.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\storport\nf-storport-storportasyncnotificationdetected.md">StorPortAsyncNotificationDetected</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportsetunitattributes.md">StorPortSetUnitAttributes</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_UNIT_ATTRIBUTES structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
