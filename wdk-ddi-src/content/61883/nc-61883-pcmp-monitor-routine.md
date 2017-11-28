---
UID: NC.61883.PCMP_MONITOR_ROUTINE
title: PCMP_MONITOR_ROUTINE
author: windows-driver-content
description: This routine is called for plug monitoring.
old-location: ieee\pcmp_monitor_routine.htm
old-project: IEEE
ms.assetid: E140D097-EE2F-4179-A43D-570397459762
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: TOPOLOGY_MAP, TOPOLOGY_MAP, *PTOPOLOGY_MAP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: 61883.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CmpMonitorRoutine
req.alt-loc: 61883.h
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
---

# PCMP_MONITOR_ROUTINE callback



## -description
<p>This routine is called for plug monitoring.</p>


## -prototype

````
PCMP_MONITOR_ROUTINE CmpMonitorRoutine;

void CmpMonitorRoutine(
  _In_ PCMP_MONITOR_INFO MonitorInfo
)
{ ... }

typedef PCMP_MONITOR_ROUTINE CmpMonitorRoutine;
````


## -parameters
<dl>

### -param <i><i>MonitorInfo</i></i> [in]

<dd>
<p>Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537050">CMP_MONITOR_INFO</a> structure containing the contents of the plug that was modified. </p>
</dd>
</dl>

## -returns
<p>This callback does not return a value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>61883.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20PCMP_MONITOR_ROUTINE callback function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
