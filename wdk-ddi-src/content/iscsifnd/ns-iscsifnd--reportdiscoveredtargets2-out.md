---
UID: NS.iscsifnd._ReportDiscoveredTargets2_OUT
title: ReportDiscoveredTargets2_OUT
author: windows-driver-content
description: The ReportDiscoveredTargets2_OUT structure holds the output data for the ReportDiscoveredTargets2 method.
old-location: storage\reportdiscoveredtargets2_out.htm
old-project: storage
ms.assetid: 24e47733-14c2-4d2c-8b0a-8cdfd68c8b3b
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ReportDiscoveredTargets2_OUT, ReportDiscoveredTargets2_OUT, *PReportDiscoveredTargets2_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsifnd.h
req.include-header: Iscsifnd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ReportDiscoveredTargets2_OUT
req.alt-loc: iscsifnd.h
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

# ReportDiscoveredTargets2_OUT structure



## -description
<p>The ReportDiscoveredTargets2_OUT structure holds the output data for the <a href="storage.reportdiscoveredtargets2">ReportDiscoveredTargets2</a> method.</p>


## -syntax

````
typedef struct _ReportDiscoveredTargets2_OUT {
  ULONG                   Status;
  ULONG                   TargetCount;
  ISCSI_DiscoveredTarget2 Targets[1];
} ReportDiscoveredTargets2_OUT, *PReportDiscoveredTargets2_OUT;
````


## -struct-fields
<dl>

### -field Status

<dd>
<p>On output, the status of the <b>ReportDiscoveredTargets</b> operation. For a list of status qualifiers, see <a href="storage.iscsi_status_qualifiers">ISCSI_STATUS_QUALIFIERS</a>. </p>
</dd>

### -field TargetCount

<dd>
<p>On output, the number of targets that are discovered. </p>
</dd>

### -field Targets

<dd>
<p>On output, an array of <a href="..\iscsifnd\ns-iscsifnd--iscsi-discoveredtarget2.md">ISCSI_DiscoveredTarget2</a> structures, which provide information that is related to discovered targets. </p>
</dd>
</dl>

## -remarks
<p>You must implement this method.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iscsifnd.h (include Iscsifnd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\iscsifnd\ns-iscsifnd--iscsi-discoveredtarget2.md">ISCSI_DiscoveredTarget2</a>
</dt>
<dt>
<a href="storage.iscsi_status_qualifiers">ISCSI_STATUS_QUALIFIERS</a>
</dt>
<dt>
<a href="storage.reportdiscoveredtargets2">ReportDiscoveredTargets2</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ReportDiscoveredTargets2_OUT structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
