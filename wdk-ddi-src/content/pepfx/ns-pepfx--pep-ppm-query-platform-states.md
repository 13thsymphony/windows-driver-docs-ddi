---
UID: NS.pepfx._PEP_PPM_QUERY_PLATFORM_STATES
title: PEP_PPM_QUERY_PLATFORM_STATES
author: windows-driver-content
description: The PEP_PPM_QUERY_PLATFORM_STATES structure specifies the number of platform idle states the hardware platform supports.
old-location: kernel\pep_ppm_query_platform_states.htm
old-project: kernel
ms.assetid: 488EC668-15B9-4B6F-B8AA-3142DB87D19B
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PEP_PPM_QUERY_PLATFORM_STATES, PEP_PPM_QUERY_PLATFORM_STATES, *PPEP_PPM_QUERY_PLATFORM_STATES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_PPM_QUERY_PLATFORM_STATES
req.alt-loc: pepfx.h
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
---

# PEP_PPM_QUERY_PLATFORM_STATES structure



## -description
<p>The <b>PEP_PPM_QUERY_PLATFORM_STATES</b> structure specifies the number of platform idle states the hardware platform supports.</p>


## -syntax

````
typedef struct _PEP_PPM_QUERY_PLATFORM_STATES {
  ULONG PlatformStateCount;
} PEP_PPM_QUERY_PLATFORM_STATES, *PPEP_PPM_QUERY_PLATFORM_STATES;
````


## -struct-fields
<dl>

### -field <b>PlatformStateCount</b>

<dd>
<p>The number of platform idle states supported by the platform.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="kernel.pep_notify_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_notify_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_PLATFORM_STATES structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
