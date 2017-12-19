---
UID: NF.dmusicks.IMiniportDMus.Service
title: IMiniportDMus::Service method
author: windows-driver-content
description: This method does not currently need to be implemented in the miniport driver. The Service method is currently unused.
old-location: audio\iminiportdmus_service.htm
old-project: audio
ms.assetid: a3f8d3f2-180c-454b-8e15-57c479c00db9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportDMus, IMiniportDMus::Service, Service
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMiniportDMus.Service
req.alt-loc: dmusicks.h
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

# IMiniportDMus::Service method



## -description

   This method does not currently need to be implemented in the miniport driver. The<code> Service</code> method is currently unused.



## -syntax

````
VOID Service(
    None
);
````


## -parameters

### -param None 


## -returns
None


## -remarks
<code>Service</code> was intended to be called during a deferred procedure call (DPC) and was to be executed as the result of a call of the <a href="audio.iportdmus_notify">IPortDMus::Notify</a> method. Instead, the DMus port driver sends notification to the miniport driver's input stream by calling <a href="audio.imxf_putmessage">IMXF::PutMessage</a> with a <b>NULL</b> parameter value. Hence, <code>Service</code> is currently unused.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dmusicks.h (include Dmusicks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dmusicks\nn-dmusicks-iminiportdmus.md">IMiniportDMus</a>
</dt>
<dt>
<a href="audio.iportdmus_notify">IPortDMus::Notify</a>
</dt>
<dt>
<a href="audio.imxf_putmessage">IMXF::PutMessage</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportDMus::Service method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
