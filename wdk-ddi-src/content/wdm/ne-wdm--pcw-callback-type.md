---
UID: NE.wdm._PCW_CALLBACK_TYPE
title: PCW_CALLBACK_TYPE
author: windows-driver-content
description: The PCW_CALLBACK_TYPE enumeration defines the notification type to send to the registered provider of the counter set. A provider passes a pointer to this enumeration as a parameter to the PcwCallback function.
old-location: devtest\pcw_callback_type.htm
old-project: devtest
ms.assetid: 92f7a980-509a-44af-b480-fa8c212f4ac6
ms.author: windowsdriverdev
ms.date: 11/21/2017
ms.keywords: WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCW_CALLBACK_TYPE
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# PCW_CALLBACK_TYPE enumeration



## -description
<p>The <b>PCW_CALLBACK_TYPE</b> enumeration defines the notification type to send to the registered provider of the counter set. A provider passes a pointer to this enumeration as a parameter to the <a href="..\wdm\nc-wdm-pcw-callback.md">PcwCallback</a> function. </p>


## -syntax

````
typedef enum _PCW_CALLBACK_TYPE { 
  PcwCallbackAddCounter          = 0,
  PcwCallbackRemoveCounter       = 1,
  PcwCallbackEnumerateInstances  = 2,
  PcwCallbackCollectData         = 3
} PCW_CALLBACK_TYPE, *PPCW_CALLBACK_TYPE;
````


## -enum-fields
<dl>

### -field PcwCallbackAddCounter

<dd>
<p>The provider is asked to add an instance of the counter set.</p>
</dd>

### -field PcwCallbackRemoveCounter

<dd>
<p>The provider is asked to remove an instance of the counter set.</p>
</dd>

### -field PcwCallbackEnumerateInstances

<dd>
<p>The provider is asked to enumerate instances of the counter set.</p>
</dd>

### -field PcwCallbackCollectData

<dd>
<p>The provider is asked to collect data from an instance of the counter set.</p>
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
<dt>Wdm.h (include Wdm.h or Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-pcw-callback.md">PcwCallback</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20PCW_CALLBACK_TYPE enumeration%20 RELEASE:%20(11/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
