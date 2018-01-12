---
UID: NF:portcls.IMiniportMidi.Service
title: IMiniportMidi::Service method
author: windows-driver-content
description: The Service method notifies the miniport driver of a request for service.
old-location: audio\iminiportmidi_service.htm
old-project: audio
ms.assetid: 7ec2c54d-3974-43e9-9ef8-63393b2d02cd
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportMidi, IMiniportMidi::Service, Service
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMiniportMidi.Service
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IMiniportMidi::Service method



## -description
The <code>Service</code> method notifies the miniport driver of a request for service.



## -syntax

````
void Service(
    None
);
````


## -parameters

### -param None 


## -returns
None


## -remarks
When the port driver calls the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536709">IMiniportMidi::Init</a> method, that method outputs a reference to the miniport driver's <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> object. The port driver adds its own <a href="..\portcls\nn-portcls-iservicesink.md">IServiceSink</a> object to this service group and then waits to receive notification of a service request. The source of the notification is typically the miniport driver's interrupt service routine (ISR).

When the miniport driver's ISR calls the port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536893">IPortMidi::Notify</a> routine, the port driver queues a deferred procedure call (DPC). When the DPC executes, it calls the <b>RequestService</b> method on each of the <b>IServiceSink</b> objects in the service group. When the DPC calls this method on the port driver's <b>IServiceSink</b> object, the port driver in turn calls the miniport driver's <code>Service</code> method. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iminiportmidi.md">IMiniportMidi</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536709">IMiniportMidi::Init</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iservicesink.md">IServiceSink</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536893">IPortMidi::Notify</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportMidi::Service method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

