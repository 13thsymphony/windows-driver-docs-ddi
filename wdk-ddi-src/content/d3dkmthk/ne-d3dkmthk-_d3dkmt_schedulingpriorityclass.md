---
UID: NE.d3dkmthk._D3DKMT_SCHEDULINGPRIORITYCLASS
title: _D3DKMT_SCHEDULINGPRIORITYCLASS
author: windows-driver-content
description: The D3DKMT_SCHEDULINGPRIORITYCLASS enumeration type contains values that describe the scheduling priority for a process.
old-location: display\d3dkmt_schedulingpriorityclass.htm
old-project: display
ms.assetid: d42e37d0-0ba9-4b79-903d-fdbb478ab196
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_SCHEDULINGPRIORITYCLASS, D3DKMT_SCHEDULINGPRIORITYCLASS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_SCHEDULINGPRIORITYCLASS
req.alt-loc: d3dkmthk.h
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

# _D3DKMT_SCHEDULINGPRIORITYCLASS enumeration



## -description
The D3DKMT_SCHEDULINGPRIORITYCLASS enumeration type contains values that describe the scheduling priority for a process.


## -syntax

````
typedef enum _D3DKMT_SCHEDULINGPRIORITYCLASS { 
  D3DKMT_SCHEDULINGPRIORITYCLASS_IDLE          = 0,
  D3DKMT_SCHEDULINGPRIORITYCLASS_BELOW_NORMAL  = 1,
  D3DKMT_SCHEDULINGPRIORITYCLASS_NORMAL        = 2,
  D3DKMT_SCHEDULINGPRIORITYCLASS_ABOVE_NORMAL  = 3,
  D3DKMT_SCHEDULINGPRIORITYCLASS_HIGH          = 4,
  D3DKMT_SCHEDULINGPRIORITYCLASS_REALTIME      = 5
} D3DKMT_SCHEDULINGPRIORITYCLASS;
````


## -enum-fields

### -field D3DKMT_SCHEDULINGPRIORITYCLASS_IDLE

The process is idle.

### -field D3DKMT_SCHEDULINGPRIORITYCLASS_BELOW_NORMAL

The scheduling priority of the process is below normal.

### -field D3DKMT_SCHEDULINGPRIORITYCLASS_NORMAL

The scheduling priority of the process is normal.

### -field D3DKMT_SCHEDULINGPRIORITYCLASS_ABOVE_NORMAL

The scheduling priority of the process is above normal.

### -field D3DKMT_SCHEDULINGPRIORITYCLASS_HIGH

The scheduling priority of the process is high.

### -field D3DKMT_SCHEDULINGPRIORITYCLASS_REALTIME

The scheduling priority of the process is in real time.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmtgetprocessschedulingpriorityclass">D3DKMTGetProcessSchedulingPriorityClass</a>
</dt>
<dt>
<a href="display.d3dkmtsetprocessschedulingpriorityclass">D3DKMTSetProcessSchedulingPriorityClass</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SCHEDULINGPRIORITYCLASS enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
