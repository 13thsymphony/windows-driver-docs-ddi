---
UID: NE.d3dkmddi._DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS
title: DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS
author: windows-driver-content
description: DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS provides additional information to the driver in a DxgkCbHardwareContentProtectionTeardown call.
old-location: display\dxgk_hardware_content_protection_teardown_flags.htm
old-project: display
ms.assetid: C9D2763D-D129-429C-AA30-85EF4D30F730
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS
req.alt-loc: d3dkmddi.h
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

# DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS enumeration



## -description
<p><b>DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS</b> provides additional information to the driver in a <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb-hardwarecontentprotectionteardown.md">DxgkCbHardwareContentProtectionTeardown</a> call.</p>


## -syntax

````
typedef enum _DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS { 
  DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAG_PREEMPTIVE  = 1
} DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS;
````


## -enum-fields
<dl>

### -field DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAG_PREEMPTIVE

<dd>
<p>Indicates that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb-hardwarecontentprotectionteardown.md">DxgkCbHardwareContentProtectionTeardown</a> callback is being preemptively called prior to tear-down event actually occurring.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb-hardwarecontentprotectionteardown.md">DxgkCbHardwareContentProtectionTeardown</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
