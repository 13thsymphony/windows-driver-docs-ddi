---
UID : NS:ks.KSINTERVAL
title : KSINTERVAL
author : windows-driver-content
description : The KSINTERVAL structure specifies a base time and time interval for recurring events.
old-location : stream\ksinterval.htm
old-project : stream
ms.assetid : 9e363bd1-3bfd-48cc-adc1-a14d23868a57
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.ksinterval, ks/KSINTERVAL, ks/PKSINTERVAL, KSINTERVAL, PKSINTERVAL, *PKSINTERVAL, ks-struct_56fded71-9af4-46a7-b872-1660582179ad.xml, PKSINTERVAL structure pointer [Streaming Media Devices], KSINTERVAL structure [Streaming Media Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PKSINTERVAL, KSINTERVAL"
---

# KSINTERVAL structure
The KSINTERVAL structure specifies a base time and time interval for recurring events.

## Syntax
````
typedef struct {
  LONGLONG TimeBase;
  LONGLONG Interval;
} KSINTERVAL, *PKSINTERVAL;
````

## Members


`Interval`

Specifies a recurrence interval, also 64-bit.

`TimeBase`

Specifies a 64-bit time base.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561811">KSEVENT_CLOCK_POSITION_MARK</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561805">KSEVENT_CLOCK_INTERVAL_MARK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSINTERVAL structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>