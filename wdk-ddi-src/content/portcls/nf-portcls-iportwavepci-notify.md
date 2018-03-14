---
UID: NF:portcls.IPortWavePci.Notify
title: IPortWavePci::Notify method
author: windows-driver-content
description: The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred.
old-location: audio\iportwavepci_notify.htm
old-project: audio
ms.assetid: fa65b3c3-196c-4cf4-8c9e-c0c9a33b2881
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IPortWavePci, IPortWavePci interface [Audio Devices], Notify method, IPortWavePci::Notify, Notify method [Audio Devices], Notify method [Audio Devices], IPortWavePci interface, Notify,IPortWavePci.Notify, audio.iportwavepci_notify, audmp-routines_5b988b85-05d1-4a66-b04d-fdd21dcf0310.xml, portcls/IPortWavePci::Notify
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortWavePci.Notify
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# Notify method
The <code>Notify</code> method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred.

## Syntax

````
void Notify(
  [in] PSERVICEGROUP ServiceGroup
);
````

## Parameters

`ServiceGroup`

A pointer to the miniport driver's <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> object.


## Return Value

None

## Remarks

Some miniport drivers call this method from an ISR in response to a hardware interrupt after having cleared the interrupt source. Other drivers call this method from a timer DPC that is scheduled to run at regular intervals. As a general rule, only drivers that manage a single render stream from KMixer should rely on hardware interrupts. Drivers that support DirectSound hardware acceleration should turn off hardware interrupts and use timer DPCs instead. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536909">IPortWavePciStream::GetMapping</a>.

Although the miniport driver is free to choose its own technique for determining when to call this method, this method should be called frequently enough to allow the port driver to fire pending position and clock events at regular intervals. Timing for this method is not as critical as it is for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536903">IPortWaveCyclic::Notify</a> method, however.

When an adapter driver installs an ISR, it submits a <i>ServiceContext</i> parameter along with the ISR's entry point (for details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559930">Providing ISR Context Information</a>). When the interrupt occurs, the operating system calls the ISR and passes <i>ServiceContext</i> as a call parameter to the ISR. Although the meaning of the <i>ServiceContext</i> parameter is known only to the driver developer, it is typically a pointer to the miniport object. The ISR uses this pointer to access information about the miniport object.

The <i>ServiceGroup</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | Any level |

## See Also

<a href="..\portcls\nn-portcls-iportwavepci.md">IPortWavePci</a>



<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536903">IPortWaveCyclic::Notify</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536909">IPortWavePciStream::GetMapping</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWavePci::Notify method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>