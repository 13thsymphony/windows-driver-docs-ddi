---
UID: NS.pmi._PMI_THRESHOLD_CONFIGURATION
title: PMI_THRESHOLD_CONFIGURATION
author: windows-driver-content
description: The PMI_THRESHOLD_CONFIGURATION structure contains information about the threshold configuration of the power meter.
old-location: powermeter\pmi_threshold_configuration.htm
ms.assetid: f2a76389-575d-425b-afe6-27fb93e101eb
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: powermeter
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PMI_THRESHOLD_CONFIGURATION
req.alt-loc: pmi.h
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
ms.keywords: PMI_THRESHOLD_CONFIGURATION, PMI_THRESHOLD_CONFIGURATION, *PPMI_THRESHOLD_CONFIGURATION
req.iface: 
---

# PMI_THRESHOLD_CONFIGURATION structure



## -description
<p>The PMI_THRESHOLD_CONFIGURATION structure contains information about the threshold configuration of the power meter.</p>


## -syntax

````
typedef struct _PMI_THRESHOLD_CONFIGURATION {
  ULONG LowerThreshold;
  ULONG UpperThreshold;
} PMI_THRESHOLD_CONFIGURATION, *PPMI_THRESHOLD_CONFIGURATION;
````


## -struct-fields
<dl>

### -field <b>LowerThreshold</b>

<dd>
<p>The lower threshold of the power meter, in units of milliwatts (mW).</p>
</dd>

### -field <b>UpperThreshold</b>

<dd>
<p>The upper threshold of the power meter, in units of milliwatts (mW).</p>
</dd>
</dl>

## -remarks
<p>The PMI_THRESHOLD_CONFIGURATION structure specifies the current configuration of the power meter's thresholds.  The <b>LowerThreshold</b> and <b>UpperThreshold</b> members specify the lower and upper range of the threshold respectively.  </p>

<p>A Power Meter Interface (PMI) event is signaled when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543847">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a> I/O control (IOCTL) request completes when one of the following occurs:</p>

<p>Power levels that are monitored by the power meter drop below the <b>LowerThreshold</b> value.</p>

<p>Power levels that are monitored by the power meter drop below the <b>UpperThreshold</b> value.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pmi.h (include Pmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543847">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_THRESHOLD_CONFIGURATION structure%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
