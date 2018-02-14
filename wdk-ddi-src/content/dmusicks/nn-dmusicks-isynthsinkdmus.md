---
UID: NN:dmusicks.ISynthSinkDMus
title: ISynthSinkDMus
author: windows-driver-content
description: The ISynthSinkDMus interface handles wave output for a DirectMusic synthesizer device.
old-location: audio\isynthsinkdmus.htm
old-project: audio
ms.assetid: 3bff4242-3e7b-424e-ac86-121267a2c32a
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.isynthsinkdmus, ISynthSinkDMus interface [Audio Devices], ISynthSinkDMus interface [Audio Devices], described, ISynthSinkDMus, dmusicks/ISynthSinkDMus, audmp-routines_744ae6c7-7f7e-4a66-9624-5a5d82e2eb86.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dmusicks.h
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
req.lib: dmusicks.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dmusicks.h
apiname:
-	ISynthSinkDMus
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# ISynthSinkDMus interface

The <code>ISynthSinkDMus</code> interface handles wave output for a DirectMusic synthesizer device. The DMus miniport driver provides this interface for use by the wave sink, which calls the methods in the interface to render wave output and to synchronize its sample clock to the master clock. As explained in <a href="https://msdn.microsoft.com/dbd6b95e-f8c8-49f1-ad90-b34821772391">Synthesizer Miniport Driver Overview</a>, the wave sink is implemented in the DMus port driver. To determine whether a DMus miniport driver supports the <code>ISynthSinkDMus</code> interface, the DMus port driver calls the miniport driver stream object's <b>IMXF::QueryInterface</b> method with REFIID <b>IID_ISynthSinkDMus</b>. <code>ISynthSinkDMus</code> inherits from the <a href="..\dmusicks\nn-dmusicks-imxf.md">IMXF</a> interface.

The <code>ISynthSinkDMus</code> interface provides methods to render, convert sample to reference time, convert reference to sample time, and synchronize to the master clock. For information about the use of the <code>ISynthSinkDMus</code> interface, see <a href="https://msdn.microsoft.com/37ba9ad5-8b35-4252-a6fd-46dead924294">A Wave Sink for Kernel-Mode Software Synthesizers</a>.

## Methods

<p>The <b>ISynthSinkDMus</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [dmusicks.ISynthSinkDMus.RefTimeToSample](nf-dmusicks-isynthsinkdmus-reftimetosample.md) | The RefTimeToSample method converts a reference time into a sample time. |
| [dmusicks.ISynthSinkDMus.Render](nf-dmusicks-isynthsinkdmus-render.md) | The Render method renders wave data into a destination sink. |
| [dmusicks.ISynthSinkDMus.SampleToRefTime](nf-dmusicks-isynthsinkdmus-sampletoreftime.md) | The SampleToRefTime method converts a sample time to a reference time. |
| [dmusicks.ISynthSinkDMus.SyncToMaster](nf-dmusicks-isynthsinkdmus-synctomaster.md) | The SyncToMaster method allows synchronization to the master clock in order to avoid drift. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dmusicks.h |