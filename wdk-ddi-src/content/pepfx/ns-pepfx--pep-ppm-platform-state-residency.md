---
UID: NS.pepfx._PEP_PPM_PLATFORM_STATE_RESIDENCY
title: PEP_PPM_PLATFORM_STATE_RESIDENCY
author: windows-driver-content
description: The PEP_PPM_PLATFORM_STATE_RESIDENCY structure specifies the accumulated residency time and transition count for a particular platform idle state.
old-location: kernel\pep_ppm_platform_state_residency.htm
old-project: kernel
ms.assetid: 35DB4043-F1B6-43C0-B8E7-FCEFF1E7E459
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PEP_PPM_PLATFORM_STATE_RESIDENCY, PEP_PPM_PLATFORM_STATE_RESIDENCY, *PPEP_PPM_PLATFORM_STATE_RESIDENCY
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
req.alt-api: PEP_PPM_PLATFORM_STATE_RESIDENCY
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

# PEP_PPM_PLATFORM_STATE_RESIDENCY structure



## -description
<p>The <b>PEP_PPM_PLATFORM_STATE_RESIDENCY</b> structure specifies the accumulated residency time and transition count for a particular platform idle state.</p>


## -syntax

````
typedef struct _PEP_PPM_PLATFORM_STATE_RESIDENCY {
  ULONG64 Residency;
  ULONG64 TransitionCount;
} PEP_PPM_PLATFORM_STATE_RESIDENCY, *PPEP_PPM_PLATFORM_STATE_RESIDENCY;
````


## -struct-fields
<dl>

### -field Residency

<dd>
<p>The accumulated residency time, in 100-nanosecond units. This is the total amount of time that the hardware platform has spent in this idle state since system startup.</p>
</dd>

### -field TransitionCount

<dd>
<p>The total number of times that the platform has entered this idle state since system startup.</p>
</dd>
</dl>

## -remarks
<p>The <b>States</b> member of the <a href="..\pepfx\ns-pepfx--pep-ppm-platform-state-residencies.md">PEP_PPM_PLATFORM_STATE_RESIDENCIES</a> structure is a pointer to an array of <b>PEP_PPM_PLATFORM_STATE_RESIDENCY</b> structures.</p>

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
<a href="..\pepfx\ns-pepfx--pep-ppm-platform-state-residencies.md">PEP_PPM_PLATFORM_STATE_RESIDENCIES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_PLATFORM_STATE_RESIDENCY structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
