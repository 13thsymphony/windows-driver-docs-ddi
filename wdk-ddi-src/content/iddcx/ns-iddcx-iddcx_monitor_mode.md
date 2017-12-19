---
UID: NS.IDDCX.IDDCX_MONITOR_MODE
title: IDDCX_MONITOR_MODE
author: windows-driver-content
description: Gives information about the current monitor mode.
old-location: display\iddcx_monitor_mode.htm
old-project: display
ms.assetid: 95e1778a-4f65-40ee-8ad2-f797ce9e95b0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IDDCX_MONITOR_MODE,
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
req.alt-api: IDDCX_MONITOR_MODE
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
req.irql: 
---

# IDDCX_MONITOR_MODE structure



## -description

                 Gives information about the current monitor mode.



## -syntax

````
typedef struct IDDCX_MONITOR_MODE {
  UINT                            Size;
  IDDCX_MONITOR_MODE_ORIGIN       Origin;
  DISPLAYCONFIG_VIDEO_SIGNAL_INFO MonitorVideoSignalInfo;
} IDDCX_MONITOR_MODE, *IDDCX_MONITOR_MODE;
````


## -struct-fields

### -field Size


                     Total size of the structure.
                 


### -field Origin


                     Where the driver derived this mode from.
                 


### -field MonitorVideoSignalInfo


                     This is the details of the Monitor mode.

<div class="alert"><b>Note</b>  The<a href="display.displayconfig_video_signal_info">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a><b>AdditionalSignalInfo</b> value vSyncFreqDivider has to have a zero value.</div>
<div> </div>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>