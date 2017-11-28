---
UID: NS.pepfx._PEP_PPM_IDLE_EXECUTE
title: PEP_PPM_IDLE_EXECUTE
author: windows-driver-content
description: The PEP_PPM_IDLE_EXECUTE structure specifies the idle state that the processor is to enter.
old-location: kernel\pep_ppm_idle_execute.htm
old-project: kernel
ms.assetid: 88BE0C4E-0607-48D6-B0E1-7B35BFD70AD4
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: PEP_PPM_IDLE_EXECUTE, PEP_PPM_IDLE_EXECUTE, *PPEP_PPM_IDLE_EXECUTE
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
req.alt-api: PEP_PPM_IDLE_EXECUTE
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

# PEP_PPM_IDLE_EXECUTE structure



## -description
<p>The <b>PEP_PPM_IDLE_EXECUTE</b> structure specifies the idle state that the processor is to enter.</p>


## -syntax

````
typedef struct _PEP_PPM_IDLE_EXECUTE {
  NTSTATUS Status;
  ULONG    ProcessorState;
  ULONG    PlatformState;
} PEP_PPM_IDLE_EXECUTE, *PPEP_PPM_IDLE_EXECUTE;
````


## -struct-fields
<dl>

### -field <b>Status</b>

<dd>
<p>[out] An <b>NTSTATUS</b> value that indicates whether the processor idle state transition was successful. The platform extension plug-in (PEP) sets this member to <b>STATUS_SUCCESSFUL</b> if the transition succeeded. Otherwise, this member is set to an appropriate error status code.</p>
</dd>

### -field <b>ProcessorState</b>

<dd>
<p>[in] The index of the processor idle state that the processor is to enter. The PEP previously specified the supported processor idle states in response to a <a href="kernel.pep_notify_ppm_query_idle_states">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a> notification. If the PEP specified N processor idle states, valid processor-idle-state indexes range from 0 to N-1.</p>
</dd>

### -field <b>PlatformState</b>

<dd>
<p>[in] The index of the platform idle state that the hardware platform will enter when the processor enters the processor idle state specified by <b>ProcessorState</b>. The PEP previously specified the supported platform idle states in response to a <a href="kernel.pep_notify_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification. If the PEP specified M platform idle states, valid platform-idle-state indexes range from 0 to M-1. If no change in platform idle state will occur, this member will contain the value P<b>EP_PLATFORM_IDLE_STATE_NONE</b> (0xffffffff).</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="kernel.pep_notify_ppm_idle_execute">PEP_NOTIFY_PPM_IDLE_EXECUTE</a> notification. The <b>ProcessorState</b> and <b>PlatformState</b> members contain input values that are supplied by the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx). The <b>Status</b> member contains an output value that the PEP writes to this member.</p>

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
<a href="kernel.pep_notify_ppm_idle_execute">PEP_NOTIFY_PPM_IDLE_EXECUTE</a>
</dt>
<dt>
<a href="kernel.pep_notify_ppm_query_idle_states">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a>
</dt>
<dt>
<a href="kernel.pep_notify_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_IDLE_EXECUTE structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
