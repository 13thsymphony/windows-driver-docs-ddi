---
UID: NS.d3dkmdt._D3DKMDT_PREEMPTION_CAPS
title: D3DKMDT_PREEMPTION_CAPS
author: windows-driver-content
description: Specifies the capabilities for the preemption of graphic processing unit (GPU) graphics requests that the display miniport driver supports.
old-location: display\d3dkmdt_preemption_caps.htm
ms.assetid: 52172edc-77a9-46b9-8382-c57c65b80b93
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_PREEMPTION_CAPS
req.alt-loc: D3dkmdt.h
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
ms.keywords: D3DKMDT_PREEMPTION_CAPS, D3DKMDT_PREEMPTION_CAPS
req.iface: 
---

# D3DKMDT_PREEMPTION_CAPS structure



## -description
<p>Specifies the capabilities for the preemption of graphic processing unit (GPU) graphics requests that the display miniport driver supports.</p>


## -syntax

````
typedef struct _D3DKMDT_PREEMPTION_CAPS {
  D3DKMDT_GRAPHICS_PREEMPTION_GRANULARITY GraphicsPreemptionGranularity;
  D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY  ComputePreemptionGranularity;
} D3DKMDT_PREEMPTION_CAPS;
````


## -struct-fields
<dl>

### -field <b>GraphicsPreemptionGranularity</b>

<dd>
<p>A  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439329">D3DKMDT_GRAPHICS_PREEMPTION_GRANULARITY</a> value that specifies the level of graphics requests  that the driver can preempt for GPU graphics  operations.</p>
</dd>

### -field <b>ComputePreemptionGranularity</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/hh439326">D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY</a> value that specifies the level of graphics requests that the driver can preempt for GPU compute shader operations.</p>
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
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439326">D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439329">D3DKMDT_GRAPHICS_PREEMPTION_GRANULARITY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_PREEMPTION_CAPS structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
