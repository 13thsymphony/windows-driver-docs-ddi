---
UID: NS.wdm._KDPC_WATCHDOG_INFORMATION
title: KDPC_WATCHDOG_INFORMATION
author: windows-driver-content
description: The KDPC_WATCHDOG_INFORMATION structure holds time-out information about the current deferred procedure call (DPC).
old-location: kernel\dpc_watchdog_information.htm
old-project: kernel
ms.assetid: 8b0d3fd8-0952-4cfa-81e1-255145fd27dd
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KDPC_WATCHDOG_INFORMATION, KDPC_WATCHDOG_INFORMATION, *PKDPC_WATCHDOG_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KDPC_WATCHDOG_INFORMATION
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# KDPC_WATCHDOG_INFORMATION structure



## -description
<p>The <b>KDPC_WATCHDOG_INFORMATION</b> structure holds time-out information about the current deferred procedure call (DPC). </p>


## -syntax

````
typedef struct _KDPC_WATCHDOG_INFORMATION {
  ULONG DpcTimeLimit;
  ULONG DpcTimeCount;
  ULONG DpcWatchdogLimit;
  ULONG DpcWatchdogCount;
  ULONG Reserved;
} KDPC_WATCHDOG_INFORMATION, *PKDPC_WATCHDOG_INFORMATION;
````


## -struct-fields
<dl>

### -field <b>DpcTimeLimit</b>

<dd>
<p>Time limit for a single, current deferred procedure call. If DPC time-out has been disabled, this value is set to 0.</p>
</dd>

### -field <b>DpcTimeCount</b>

<dd>
<p>Time remaining for the current deferred procedure call, if DPC time-out has been enabled.</p>
</dd>

### -field <b>DpcWatchdogLimit</b>

<dd>
<p>Total time limit permitted for a sequence of deferred procedure calls. If DPC watchdog has been disabled, this value is set to zero.</p>
</dd>

### -field <b>DpcWatchdogCount</b>

<dd>
<p>Time value remaining for the current sequence of deferred procedure calls, if enabled.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved for system use.</p>
</dd>
</dl>

## -remarks
<p>Time figures stored in each member are dimensionless.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows Vista.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-kequerydpcwatchdoginformation.md">KeQueryDpcWatchdogInformation</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KDPC_WATCHDOG_INFORMATION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
