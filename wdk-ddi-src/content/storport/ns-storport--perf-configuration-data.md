---
UID: NS.storport._PERF_CONFIGURATION_DATA
title: PERF_CONFIGURATION_DATA
author: windows-driver-content
description: The PERF_CONFIGURATION_DATA structure describes the performance optimizations that are supported by the StorPortInitializePerfOpts routine.
old-location: storage\perf_configuration_data.htm
old-project: storage
ms.assetid: 47db8f0f-9f3b-44d9-8110-dc0b79d0e26a
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PERF_CONFIGURATION_DATA, PERF_CONFIGURATION_DATA, *PPERF_CONFIGURATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PERF_CONFIGURATION_DATA
req.alt-loc: storport.h
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

# PERF_CONFIGURATION_DATA structure



## -description
<p>The PERF_CONFIGURATION_DATA structure describes the performance optimizations that are supported by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567114">StorPortInitializePerfOpts</a> routine.</p>


## -syntax

````
typedef struct _PERF_CONFIGURATION_DATA {
  ULONG           Version;
  ULONG           Size;
  ULONG           Flags;
  ULONG           ConcurrentChannels;
  ULONG           FirstRedirectionMessageNumber;
  ULONG           LastRedirectionMessageNumber;
  ULONG           DeviceNode;
  ULONG           Reserved;
  PGROUP_AFFINITY MessageTargets;
} PERF_CONFIGURATION_DATA, *PPERF_CONFIGURATION_DATA;
````


## -struct-fields
<dl>

### -field <b>Version</b>

<dd>
<p>The version number of the structure. Set this member when querying and initializing optimizations.</p>
</dd>

### -field <b>Size</b>

<dd>
<p>The size of the structure, set to <b>sizeof(PERF_CONFIGURATION_DATA)</b>.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>A bitwise-OR of supported flags. Currently, the following flags are supported:
	  </p>
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>STOR_PERF_DPC_REDIRECTION</p>
</td>
<td>
<p>This flag is used to indicate that DPC processing should be spread out over multiple CPUs.</p>
<p>This flag is valid when <b>Version</b> is set to 2 or 3.</p>
</td>
</tr>
<tr>
<td>
<p>STOR_PERF_CONCURRENT_CHANNELS</p>
</td>
<td>
<p>This flag is used to indicate that concurrent calls to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557423">HwStorStartIo</a> routine are supported. Prior to Windows 8, miniports must not set this flag.</p>
<p>This flag is valid when <b>Version</b> is set to 2 or 3.</p>
</td>
</tr>
<tr>
<td>
<p>STOR_PERF_INTERRUPT_MESSAGE_RANGES</p>
</td>
<td>
<p>This flag is used to indicate that interrupt redirection is supported. When you use this flag, you must also set the STOR_PERF_DPC_REDIRECTION flag.</p>
<p>This flag is valid when <b>Version</b> is set to 2 or 3.</p>
</td>
</tr>
<tr>
<td>
<p>STOR_PERF_ADV_CONFIG_LOCALITY</p>
</td>
<td>
<p>This flag is used to indicate that you should use the group and mask that pertain to the message group with the correct affinity. When you use this flag, you must also set the STOR_PERF_INTERRUPT_MESSAGE_RANGES and the STOR_PERF_DPC_REDIRECTION flags.</p>
<p>This flag is valid when <b>Version</b> is set to 3.</p>
</td>
</tr>
<tr>
<td>
<p>STOR_PERF_OPTIMIZE_FOR_COMPLETION_DURING_STARTIO</p>
</td>
<td>
<p>This flag is used to indicate that the miniport driver will complete I/Os concurrently with the submission of new I/Os. When you use this flag, you must also set the STOR_PERF_DPC_REDIRECTION flag.</p>
<p>This flag is valid when <b>Version</b> is set to 3. See remarks below.</p>
</td>
</tr>
<tr>
<td>
<p>STOR_PERF_DPC_REDIRECTION_CURRENT_CPU</p>
</td>
<td>
<p>This flag is used to indicate that you are opting into DPC Redirection (required) but the IO redirection choice is set to the CPU requesting the DPC and not the CPU originating the IO request into Storport.</p>
<p>When you use this flag, you must also set the STOR_PERF_DPC_REDIRECTION flag.</p>
<p>This flag is valid when <b>Version</b> is set to 4.</p>
</td>
</tr>
<tr>
<td>
<p>STOR_PERF_NO_SGL</p>
</td>
<td>
<p>This flag is used to indicate that miniport doesn't need SGLs to be created by storport driver for an IO request buffer. </p>
<p>This flag is valid when <b>Version</b> is set to 5.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>ConcurrentChannels</b>

<dd>
<p>The number of concurrent calls to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557423">HwStorStartIo</a> routine that the miniport driver and the device  support. This member is only accessed when the STOR_PERF_CONCURRENT_CHANNELS flag has been set. Prior to Windows 8, miniports must not set this value.</p>
</dd>

### -field <b>FirstRedirectionMessageNumber</b>

<dd>
<p>When the <b>Flags</b> member has the STOR_PERF_INTERRUPT_MESSAGE_RANGES flag set, the miniport driver initializes interrupt redirection to begin with this message number. This member is only accessed when the STOR_PERF_INTERRUPT_MESSAGE_RANGES flag is set.</p>
</dd>

### -field <b>LastRedirectionMessageNumber</b>

<dd>
<p>When the <b>Flags</b> member has the STOR_PERF_INTERRUPT_MESSAGE_RANGES flag set, the miniport driver initializes interrupt redirection to end with this message number. This member is only accessed when the STOR_PERF_INTERRUPT_MESSAGE_RANGES flag is set.</p>
</dd>

### -field <b>DeviceNode</b>

<dd>
<p>When the <b>Flags</b> member has the STOR_PERF_ADV_CONFIG_LOCALITY flag set, Storport initializes this field to contain the NUMA node number in which the miniport driver's device resides.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>MessageTargets</b>

<dd>
<p>When the <b>Flags</b> member has the STOR_PERF_ADV_CONFIG_LOCALITY flag set, Storport initializes the fields of in the structures of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546539">GROUP_AFFINITY</a> array. These structures correspond to the redirection messages that are currently in use. The array itself is zero-based, but <b>FirstRedirectionMessageNumber</b> is not required to be zero. The miniport allocates this array and sets <b>MessageTargets</b> to point to it. The miniport driver must allocate a <b>GROUP_AFFINITY</b> array large enough to hold all the returned affinity masks.</p>
</dd>
</dl>

## -remarks
<p>The current version of this structure is defined by <b>STOR_PERF_VERSION</b>. Setting <b>Version</b> to this value will allow <b>Flags</b> to specify all  supported optimizations.</p>

<p>The purpose of the STOR_PERF_DPC_REDIRECTION flag is to ensure that individual CPUs are not overwhelmed with DPC processing. When this flag is set, DPC processing is spread over multiple CPUs. If STOR_PERF_DPC_REDIRECTION_CURRENT_CPU is not set, StorPort will attempt to schedule I/O completion DPCs on the same CPU that originated the I/O.</p>

<p>Typically, a miniport  completes I/O requests in it's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557423">HwStorStartIo</a> routine and calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567433">StorPortNotification</a> with the <b>RequestComplete</b> notification type. For processing I/O in this manner, the miniport will leave the STOR_PERF_OPTIMIZE_FOR_COMPLETION_DURING_STARTIO flag set in the <b>Flags</b> member allowing Storport to adjust DPC redirection.</p>

<p>For information about enabling message-signaled interrupts for a device, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544246">Enabling Message-Signaled Interrupts in the Registry</a>.</p>

## -requirements
<table>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567114">StorPortInitializePerfOpts</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PERF_CONFIGURATION_DATA structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
