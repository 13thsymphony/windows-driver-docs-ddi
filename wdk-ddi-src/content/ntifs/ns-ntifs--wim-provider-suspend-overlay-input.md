---
UID: NS.ntifs._WIM_PROVIDER_SUSPEND_OVERLAY_INPUT
title: WIM_PROVIDER_SUSPEND_OVERLAY_INPUT
author: windows-driver-content
description: A Windows Image File (WIM) data source to suspend from the WIM provider is specified in the WIM_PROVIDER_SUSPEND_OVERLAY_INPUT structure.
old-location: ifsk\wim_provider_suspend_overlay_input.htm
old-project: ifsk
ms.assetid: 85BECD4F-3039-483F-8ED1-EFCA6BEE1181
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: WIM_PROVIDER_SUSPEND_OVERLAY_INPUT, WIM_PROVIDER_SUSPEND_OVERLAY_INPUT, *PWIM_PROVIDER_SUSPEND_OVERLAY_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WIM_PROVIDER_SUSPEND_OVERLAY_INPUT
req.alt-loc: ntifs.h
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

# WIM_PROVIDER_SUSPEND_OVERLAY_INPUT structure



## -description
<p>A Windows Image File (WIM) data source to suspend from the WIM provider is specified in the <b>WIM_PROVIDER_SUSPEND_OVERLAY_INPUT</b> structure.</p>


## -syntax

````
typedef struct _WIM_PROVIDER_SUSPEND_OVERLAY_INPUT {
  LARGE_INTEGER DataSourceId;
} WIM_PROVIDER_SUSPEND_OVERLAY_INPUT, *PWIM_PROVIDER_SUSPEND_OVERLAY_INPUT;
````


## -struct-fields
<dl>

### -field <b>DataSourceId</b>

<dd>
<p>An identifier value for the WIM file data source to suspend.</p>
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
<p>Available starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt426735">FSCTL_SUSPEND_OVERLAY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn632437">FSCTL_ADD_OVERLAY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn632442">FSCTL_REMOVE_OVERLAY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn632445">FSCTL_UPDATE_OVERLAY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20WIM_PROVIDER_SUSPEND_OVERLAY_INPUT structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
