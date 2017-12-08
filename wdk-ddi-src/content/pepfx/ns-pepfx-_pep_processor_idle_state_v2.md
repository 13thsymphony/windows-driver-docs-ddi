---
UID: NS.PEPFX._PEP_PROCESSOR_IDLE_STATE_V2
title: _PEP_PROCESSOR_IDLE_STATE_V2
author: windows-driver-content
description: The PEP_PROCESSOR_IDLE_STATE_V2 structure describes a processor idle state that the platform extension plug-in (PEP) supports.
old-location: kernel\pep_processor_idle_state_v2.htm
old-project: kernel
ms.assetid: DEA8B166-5236-4BE3-B16D-9EE1B34796F8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PEP_PROCESSOR_IDLE_STATE_V2, PEP_PROCESSOR_IDLE_STATE_V2, *PPEP_PROCESSOR_IDLE_STATE_V2
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
req.alt-api: PEP_PROCESSOR_IDLE_STATE_V2
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
---

# _PEP_PROCESSOR_IDLE_STATE_V2 structure



## -description
The <b>PEP_PROCESSOR_IDLE_STATE_V2</b> structure describes a processor idle state that the platform extension plug-in (PEP) supports.


## -syntax

````
typedef struct _PEP_PROCESSOR_IDLE_STATE_V2 {
  union {
    ULONG  Ulong;
    struct {
      ULONG Interruptible  :1;
      ULONG CacheCoherent  :1;
      ULONG ThreadContextRetained  :1;
      ULONG CStateType  :4;
      ULONG WakesSpuriously  :1;
      ULONG PlatformOnly  :1;
      ULONG Autonomous  :1;
      ULONG Reserved  :22;
    };
  };
  ULONG Latency;
  ULONG BreakEvenDuration;
} PEP_PROCESSOR_IDLE_STATE_V2, *PPEP_PROCESSOR_IDLE_STATE_V2;
````


## -struct-fields

### -field ( unnamed union )

A collection of flag bits and status fields that can be accessed either individually as bitfields, or together as a 32-bit unsigned integer value.

### -field Ulong

Flag bits and status fields accessed as a single 32-bit unsigned integer value.

### -field ( unnamed struct )

Flag bits and status fields accessed as individual bitfields.

### -field Interruptible

Whether the processor can respond to interrupts when in this idle state. Set this flag bit to 1 if the processor can respond to interrupts, and to 0 if it cannot.

### -field CacheCoherent

Whether the processor's local cache or caches remain coherent through the duration of this processor idle state. Set this flag bit to 1 if cache coherency is maintained in this idle state, and to 0 if it is not.

### -field ThreadContextRetained

Whether thread context is retained in this processor idle state. Set this flag bit to 1 if the processor hardware retains the thread context across the idle transition. Set to 0 if the processor uses the multiprocessor parking protocol to exit the idle state and return control to the operating system. For more information about this protocol, see the document titled "Multiprocessor Startup for ARM Platforms" at <a href="https://www.acpica.org/related-documents">https://www.acpica.org/related-documents</a>.

### -field CStateType

The C-state type of the processor idle state. Set this bitfield to zero if this idle state does not correspond to an ACPI-defined C-state. Otherwise, set this bitfield to the C-state number. That is, set <b>CStateType</b> = 1 for C1, set <b>CStateType</b> = 2 for C2, and so on. For more information about C-states, see section 8.1, "Processor Power States", of the Advanced Configuration and Control Specification, Revision 5.0 (<a href="http://www.acpi.info">ACPI 5.0 specification</a>).

### -field WakesSpuriously

Whether the processor can wake spuriously in this idle state. Set this flag bit to 0 if the processor is guaranteed to stay in this idle state until it receives a device interrupt, inter-processor interrupt (IPI), or wake request. Set to 1 if the processor might wake autonomously for some other reason.

### -field PlatformOnly

Whether the transition to this processor idle state can be performed only as part of a coordinated transition to a platform-wide idle state. Set this flag bit to 1 if the processor idle state transition can be performed only as part of a transition to a platform idle state. Otherwise, set to 0.

### -field Autonomous

Whether a coordinated transition to this processor idle state is performed autonomously by the processor hardware. Set this flag bit to 1 if these transitions are autonomous, and to 0 if they are not. A flag value of 1 indicates that the idle state can be entered without sending a <a href="kernel.pep_notify_ppm_test_idle_state">PEP_NOTIFY_PPM_TEST_IDLE_STATE</a>, <a href="kernel.pep_notify_ppm_idle_pre_execute">PEP_NOTIFY_PPM_IDLE_PRE_EXECUTE</a>, or <a href="kernel.pep_notify_ppm_idle_complete">PEP_NOTIFY_PPM_IDLE_COMPLETE</a> notification. This flag can be set to 1 only if <b>CStateType</b> is nonzero.

### -field Reserved

Reserved for future use. Set to zero.
</dd>
</dl>
</dd>
</dl>

### -field Latency

The worst-case latency, in 100-nanosecond units,  that the processor requires to wake from this idle state in response to a wake event.

### -field BreakEvenDuration

The minimum amount of time, specified in 100-nanosecond units, that the processor must spend in this idle state to make a transition to this state worthwhile. The Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx) uses this member value as a hint to avoid switching a processor to an idle state unless the processor is likely to remain in this state for at least the amount of time specified by <b>BreakEvenDuration</b>.

## -remarks
This structure is used in conjunction with the <a href="kernel.pep_notify_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. The <b>IdleStates</b>  member of the <a href="kernel.pep_ppm_query_idle_states_v2">PEP_PPM_QUERY_IDLE_STATES_V2</a> structure is the first element in an array of <b>PEP_PROCESSOR_IDLE_STATE_V2</b> structures.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported starting with Windows 10.
</td>
</tr>
<tr>
<th width="30%">
Header
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
<a href="kernel.pep_notify_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>
</dt>
<dt>
<a href="kernel.pep_ppm_query_idle_states_v2">PEP_PPM_QUERY_IDLE_STATES_V2</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PROCESSOR_IDLE_STATE_V2 structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
