---
UID: NN:portcls.IUnregisterSubdevice
title: IUnregisterSubdevice
author: windows-driver-content
description: The IUnregisterSubdevice interface implements a method to remove a registered subdevice.
old-location: audio\iunregistersubdevice.htm
old-project: audio
ms.assetid: 023b0a03-a572-459b-a1eb-b25fcde6ecc5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.iunregistersubdevice, IUnregisterSubdevice interface [Audio Devices], IUnregisterSubdevice interface [Audio Devices], described, IUnregisterSubdevice, portcls/IUnregisterSubdevice, audmp-routines_1af8aada-2816-4e82-abe4-579ba672866b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IUnregisterSubdevice
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IUnregisterSubdevice interface

The <code>IUnregisterSubdevice</code> interface implements a method to remove a registered subdevice. The port driver implements this interface. To determine whether a port driver supports the <code>IUnregisterSubdevice</code> interface, a miniport driver calls the port driver object's <b>QueryInterface</b> method with REFIID <b>IID_IUnregisterSubdevice</b>. The miniport driver is responsible for releasing the <code>IUnregisterSubdevice</code> object after it is no longer needed. The <code>IUnregisterSubdevice</code> interface inherits from <b>IUnknown</b>.

The following port drivers support the <code>IUnregisterSubdevice</code> interface:
<ul>
<li>
WaveCyclic

</li>
<li>
WavePci

</li>
<li>
Topology

</li>
<li>
DMus

</li>
<li>
MIDI

</li>
</ul>The single method in this interface unregisters a subdevice that was previously registered by a call to the <a href="..\portcls\nf-portcls-pcregistersubdevice.md">PcRegisterSubdevice</a> routine. PortCls supports <b>PcRegisterSubdevice</b>.

The <code>IUnregisterSubdevice</code> object maintains its own internal reference to the subdevice to ensure that the corresponding device object is not deleted until all references to the <code>IUnregisterSubdevice</code> object are released.

## Methods

<p>The <b>IUnregisterSubdevice</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [portcls.IUnregisterSubdevice.UnregisterSubdevice](nf-portcls-iunregistersubdevice-unregistersubdevice.md) | The UnregisterSubdevice method deletes the registration of a subdevice that was previously registered by a call to PcRegisterSubdevice. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | portcls.h |