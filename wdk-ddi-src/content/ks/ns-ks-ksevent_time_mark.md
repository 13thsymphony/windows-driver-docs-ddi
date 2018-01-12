---
UID: NS:ks.KSEVENT_TIME_MARK
title: KSEVENT_TIME_MARK
author: windows-driver-content
description: The KSEVENT_TIME_MARK structure is used in various events within the KSEVENTSETID_Clock event set.
old-location: stream\ksevent_time_mark.htm
old-project: stream
ms.assetid: c1e756a8-4850-4ddc-9bbf-97146a798554
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSEVENT_TIME_MARK, KSEVENT_TIME_MARK, *PKSEVENT_TIME_MARK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSEVENT_TIME_MARK
req.alt-loc: ks.h
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
req.typenames: KSEVENT_TIME_MARK, *PKSEVENT_TIME_MARK
---

# KSEVENT_TIME_MARK structure



## -description
The KSEVENT_TIME_MARK structure is used in various events within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561764">KSEVENTSETID_Clock</a> event set. 



## -syntax

````
typedef struct {
  KSEVENTDATA EventData;
  LONGLONG    MarkTime;
} KSEVENT_TIME_MARK, *PKSEVENT_TIME_MARK;
````


## -struct-fields

### -field EventData

A structure of type <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> that specifies the standard event structure.


### -field MarkTime

Specifies the clock time when the event should be signaled.


## -remarks
The flags indicate the type of units for the interval. The interval can be specified in KSEVENT_DATA_MARKF_FILETIME units for these events, which are 100-nanosecond units.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-ksevent_time_interval.md">KSEVENT_TIME_INTERVAL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561764">KSEVENTSETID_Clock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSEVENT_TIME_MARK structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

