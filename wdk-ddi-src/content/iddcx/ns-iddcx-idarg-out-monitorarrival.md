---
UID: NS.iddcx.IDARG_OUT_MONITORARRIVAL
title: IDARG_OUT_MONITORARRIVAL
author: windows-driver-content
description: Gives information about the monitor that is exposed to the OS.
old-location: display\idarg_out_monitorarrival.htm
old-project: display
ms.assetid: 0e5c4b23-cb62-4320-9e55-d0da67b62aa1
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: IDARG_OUT_MONITORARRIVAL,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDARG_OUT_MONITORARRIVAL
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _Must_inspect_result_
req.iface: 
---

# IDARG_OUT_MONITORARRIVAL structure



## -description
<p>Gives information about the monitor that is exposed to the OS.
             </p>


## -syntax

````
typedef struct IDARG_OUT_MONITORARRIVAL {
  LUID OsAdapterLuid;
  UINT OsTargetId;
} IDARG_OUT_MONITORARRIVAL, *IDARG_OUT_MONITORARRIVAL;
````


## -struct-fields
<dl>

### -field OsAdapterLuid

<dd>
<p>
                     LUID of the adapter where this monitor is exposed to the OS
    . </p>
<div class="alert"><b>Note</b>  There are no API/DDI calls the driver can make with this information. Its only use is to pass it to companion applications so they can identify the monitor they control.</div>
<div> </div>
</dd>

### -field OsTargetId

<dd>
<p>
                     DMM VidPn target id of the target this monitor is exposed to the OS. </p>
<div class="alert"><b>Note</b>  There are no API/DDI calls the driver can make with this information. Its only use is to pass it to companion applications so they can identify the monitor they control.</div>
<div> </div>
<div class="alert"><b>Note</b>  Although this value is related to the <a href="..\iddcx\ns-iddcx-iddcx-monitor-info.md">IDDCX_MONITOR_INFO</a> value <b>ConnectorIndex</b> passed by the driver, the OS will perform internal mapping between the two that will change in future release. As such, the driver should not take any dependencies on this mapping and should use <b>OsAdapterLuid</b> &amp; <b>OsTargetId</b> instead.</div>
<div> </div>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\iddcx\ns-iddcx-iddcx-monitor-info.md">IDDCX_MONITOR_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IDARG_OUT_MONITORARRIVAL structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
