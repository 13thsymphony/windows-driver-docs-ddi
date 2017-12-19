---
UID: NS.KS.KSINTERVAL
title: KSINTERVAL
author: windows-driver-content
description: The KSINTERVAL structure specifies a base time and time interval for recurring events.
old-location: stream\ksinterval.htm
old-project: stream
ms.assetid: 9e363bd1-3bfd-48cc-adc1-a14d23868a57
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSINTERVAL, KSINTERVAL, *PKSINTERVAL, PKSINTERVAL
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
req.alt-api: KSINTERVAL
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
---

# KSINTERVAL structure



## -description
The KSINTERVAL structure specifies a base time and time interval for recurring events.



## -syntax

````
typedef struct {
  LONGLONG TimeBase;
  LONGLONG Interval;
} KSINTERVAL, *PKSINTERVAL;
````


## -struct-fields

### -field TimeBase

Specifies a 64-bit time base.


### -field Interval

Specifies a recurrence interval, also 64-bit.


## -remarks


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561805">KSEVENT_CLOCK_INTERVAL_MARK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561811">KSEVENT_CLOCK_POSITION_MARK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSINTERVAL structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

