---
UID: NF:portcls.IInterruptSync.Connect
title: IInterruptSync::Connect method
author: windows-driver-content
description: The Connect method connects the synchronization object to the interrupt.
old-location: audio\iinterruptsync_connect.htm
old-project: audio
ms.assetid: 62cb451d-1170-4462-94ac-0477adc5946b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IInterruptSync, IInterruptSync::Connect, Connect
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
req.alt-api: IInterruptSync.Connect
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
req.irql: PASSIVE_LEVEL
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IInterruptSync::Connect method



## -description
The <code>Connect</code> method connects the synchronization object to the interrupt.



## -syntax

````
NTSTATUS Connect(
    None
);
````


## -parameters

### -param None 


## -returns
<code>Connect</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.


## -remarks
This method connects the synchronization object to the interrupt that was specified in the call to <a href="..\portcls\nf-portcls-pcnewinterruptsync.md">PcNewInterruptSync</a> that created the synchronization object. The interrupt is specified in the <b>PcNewInterruptSync</b> function's <i>ResourceList</i> and <i>ResourceIndex</i> parameters.


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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iinterruptsync.md">IInterruptSync</a>
</dt>
<dt>
<a href="..\portcls\nf-portcls-pcnewinterruptsync.md">PcNewInterruptSync</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IInterruptSync::Connect method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

