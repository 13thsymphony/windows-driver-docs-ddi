---
UID: NN:portcls.IPortClsStreamResourceManager2
title: IPortClsStreamResourceManager2
author: windows-driver-content
description: IPortClsStreamResourceManager2 is used to manage the registration of audio stream resources.
old-location: audio\iportclsstreamresourcemanager2.htm
old-project: audio
ms.assetid: B37310B5-3C74-428A-B8DF-C39B85A521C0
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPortClsStreamResourceManager2, IPortClsStreamResourceManager2 interface [Audio Devices], IPortClsStreamResourceManager2 interface [Audio Devices], described, audio.iportclsstreamresourcemanager2, portcls/IPortClsStreamResourceManager2
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortClsStreamResourceManager2
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsStreamResourceManager2 interface

IPortClsStreamResourceManager2 is used to manage the registration of audio stream resources. 

To help ensure glitch-free operation, audio drivers must register their streaming resources. This allows the OS to manage resources to avoid interference between audio streaming and other subsystems. 

Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. 


<a href="https://msdn.microsoft.com/library/windows/hardware/mt270107">IPortClsStreamResourceManager::AddStreamResource</a> expects that the caller is an audio miniport driver. <a href="https://msdn.microsoft.com/library/windows/hardware/mt604863">IPortClsStreamResourceManager2::AddStreamResource2</a> does not assume that the caller is an audio miniport driver, and requires an explicit pointer to the Physical Device Object (PDO).

The IPortClsStreamResourceManager2 interface is supported in Windows 10, version 1511 and later versions of Windows. IPortClsStreamResourceManager2 inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/mt270106">IPortClsStreamResourceManager</a> and IUnknown.

A WaveRT miniport driver optionally can use this interface instead of hard-linking with the <a href="https://msdn.microsoft.com/library/windows/hardware/mt298188">PcAddStreamResource</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/mt298189">PcRemoveStreamResource</a>. This option is very useful when the 

same audio miniport driver must run on previous versions of Windows. The audio miniport driver can query for the IID_IPortClsStreamResourceManager2 interface and register its resources only when PortCls supports the interface.

## Methods

<p>The <b>IPortClsStreamResourceManager2</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [IPortClsStreamResourceManager2::AddStreamResource2](nf-portcls-iportclsstreamresourcemanager2-addstreamresource2.md) | AddStreamResource2 adds a stream resource. Two type of stream resources are supported:\_interrupts and driver-owned threads. The AddStreamResource2 method can only be used by audio waveRT miniport drivers. |


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | portcls.h |