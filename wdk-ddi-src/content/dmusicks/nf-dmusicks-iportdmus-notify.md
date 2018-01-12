---
UID: NF:dmusicks.IPortDMus.Notify
title: IPortDMus::Notify method
author: windows-driver-content
description: The Notify method should be called from the miniport driver's interrupt service routine (ISR) when a hardware interrupt has occurred.
old-location: audio\iportdmus_notify.htm
old-project: audio
ms.assetid: 64158ea5-23ca-42a3-9284-2b1523e616b8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortDMus, IPortDMus::Notify, Notify
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
req.alt-api: IPortDMus.Notify
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
req.irql: Any level
req.typenames: DMUS_STREAM_TYPE
---

# IPortDMus::Notify method



## -description
The <code>Notify</code> method should be called from the miniport driver's interrupt service routine (ISR) when a hardware interrupt has occurred. This call requests that the port driver call the miniport driver back with a deferred procedure call (DPC) while the miniport driver handles the interrupt.



## -syntax

````
void Notify(
  [in, optional] PSERVICEGROUP pServiceGroup (optional)
);
````


## -parameters

### -param pServiceGroup (optional) [in, optional]

Pointer to an <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> object. This parameter is optional and can be specified as <b>NULL</b>. For more information, see the following Remarks section.


## -returns
None


## -remarks
The <code>Notify</code> method sends notification to the miniport driver's service group:

If the <i>pServiceGroup</i> parameter is non-<b>NULL</b>, the <code>Notify</code> method calls the <b>RequestService</b> method on the <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> object that this parameter points to.

The miniport driver typically calls <code>Notify</code> to notify the port driver that the audio device has generated a hardware interrupt. When an interrupt signals, for example, that some register needs to be read, the miniport driver's ISR cannot access the MXF (MIDI transform filter) graph at the elevated IRQL. Instead, the miniport driver can store the input data (a byte of MIDI data, for example) from the register, call <code>Notify</code>, and wait for the port driver to get back to it with a DPC.

When the miniport driver's ISR calls <code>Notify</code>, the port driver receives the notification at the elevated hardware interrupt IRQL and puts a DPC on the queue. When IRQL drops to the DISPATCH_LEVEL, the port driver's DPC fires and services the miniport driver.

Within the DPC, the port driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a> on the miniport driver's input stream with a parameter of <b>NULL</b> to signify that the miniport driver can now put the previously stored MIDI message into the MXF graph because the IRQL has dropped back to DISPATCH_LEVEL.

This method is vital for accurate timing. Most miniports will call this method in response to a notification interrupt after having cleared the interrupt source. Although the miniport driver is free to use other methods for determining when to call this method, precise timing is important and should be maintained.

When an adapter driver installs an ISR, it submits a <i>ServiceContext</i> parameter along with the ISR's entry point (for details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559930">Providing ISR Context Information</a>). When the interrupt occurs, the operating system calls the ISR and passes <i>ServiceContext</i> as a call parameter to the ISR. Although the meaning of the <i>ServiceContext</i> parameter is known only to the driver developer, it is typically a pointer to the miniport object. The ISR uses this pointer to access information about the miniport object.

The <i>pServiceGroup</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.


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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536882">IPortDMus::RegisterServiceGroup</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536700">IMiniportDMus::Init</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536701">IMiniportDMus::NewStream</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortDMus::Notify method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

