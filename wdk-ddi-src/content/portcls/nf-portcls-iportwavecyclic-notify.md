---
UID: NF.portcls.IPortWaveCyclic.Notify
title: IPortWaveCyclic::Notify
author: windows-driver-content
description: The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR).
old-location: audio\iportwavecyclic_notify.htm
old-project: audio
ms.assetid: 318ba587-e34f-4f9f-bdf9-3e7c402456c5
ms.author: windowsdriverdev
ms.date: 11/21/2017
ms.keywords: IPortWaveCyclic, Notify, IPortWaveCyclic::Notify
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortWaveCyclic.Notify
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
req.irql: Any level
req.iface: IPortWaveCyclic
---

# IPortWaveCyclic::Notify method



## -description
<p>The <code>Notify</code> method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR).</p>


## -syntax

````
void Notify(
  [in] PSERVICEGROUP ServiceGroup
);
````


## -parameters
<dl>

### -param <i>ServiceGroup</i> [in]

<dd>
<p>Pointer to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a> object.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>This method is vital for accurate timing. Miniport drivers typically call this method in response to a notification interrupt after having cleared the interrupt source. Although the miniport driver is free to use other methods for determining when to call this method, precise timing is important and should be maintained.</p>

<p>When an adapter driver installs an ISR, it submits a <i>ServiceContext</i> parameter along with the ISR's entry point (for details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559930">Providing ISR Context Information</a>). When the interrupt occurs, the operating system calls the ISR and passes <i>ServiceContext</i> as a call parameter to the ISR. Although the meaning of the <i>ServiceContext</i> parameter is known only to the driver developer, it is typically a pointer to the miniport object. The ISR uses this pointer to access information about the miniport object.</p>

<p>The port driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536719">IMiniportWaveCyclicStream::SetNotificationFreq</a> method to specify the frequency with which the ISR should call the <code>Notify</code> method. In all current Windows releases, the port driver specifies a regular interval of 10 milliseconds between successive notifications. This value might change in a future release.</p>

<p>The <i>ServiceGroup</i> parameter follows the <a href="NULL">reference-counting conventions for COM objects</a>.</p>

<p>This method is vital for accurate timing. Miniport drivers typically call this method in response to a notification interrupt after having cleared the interrupt source. Although the miniport driver is free to use other methods for determining when to call this method, precise timing is important and should be maintained.</p>

<p>When an adapter driver installs an ISR, it submits a <i>ServiceContext</i> parameter along with the ISR's entry point (for details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559930">Providing ISR Context Information</a>). When the interrupt occurs, the operating system calls the ISR and passes <i>ServiceContext</i> as a call parameter to the ISR. Although the meaning of the <i>ServiceContext</i> parameter is known only to the driver developer, it is typically a pointer to the miniport object. The ISR uses this pointer to access information about the miniport object.</p>

<p>The port driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536719">IMiniportWaveCyclicStream::SetNotificationFreq</a> method to specify the frequency with which the ISR should call the <code>Notify</code> method. In all current Windows releases, the port driver specifies a regular interval of 10 milliseconds between successive notifications. This value might change in a future release.</p>

<p>The <i>ServiceGroup</i> parameter follows the <a href="NULL">reference-counting conventions for COM objects</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536899">IPortWaveCyclic</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536719">IMiniportWaveCyclicStream::SetNotificationFreq</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWaveCyclic::Notify method%20 RELEASE:%20(11/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
