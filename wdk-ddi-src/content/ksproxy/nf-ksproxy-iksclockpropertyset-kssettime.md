---
UID : NF:ksproxy.IKsClockPropertySet.KsSetTime
title : IKsClockPropertySet::KsSetTime method
author : windows-driver-content
description : The KsSetTime method sets the current time on the underlying clock.
old-location : stream\iksclockpropertyset_kssettime.htm
old-project : stream
ms.assetid : b1489593-9458-4e78-b59d-c8a780a3a3f1
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsSetTime method [Streaming Media Devices], IKsClockPropertySet interface, ksproxy_6d169c35-dd1b-4ccb-b028-f6a8d19e51ea.xml, ksproxy/IKsClockPropertySet::KsSetTime, KsSetTime, IKsClockPropertySet, IKsClockPropertySet interface [Streaming Media Devices], KsSetTime method, IKsClockPropertySet::KsSetTime, KsSetTime method [Streaming Media Devices], stream.iksclockpropertyset_kssettime
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : ksproxy.h
req.include-header : Ksproxy.h
req.target-type : Desktop
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
req.lib : ksproxy.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PIPE_STATE
---


# KsSetTime method
The <b>KsSetTime</b> method sets the current time on the underlying clock.

## Syntax

````
HRESULT KsSetTime(
  [in] LONGLONG Time 
);
````

## Parameters

`Time`

Time to which to set the underlying clock.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565095">KSPROPERTY_CLOCK_TIME</a> property to set the current clock time.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565095">KSPROPERTY_CLOCK_TIME</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559751">IKsClockPropertySet::KsGetTime</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsClockPropertySet::KsSetTime method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>