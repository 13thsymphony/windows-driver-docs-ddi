---
UID: NN:portcls.IDrmPort2
title: IDrmPort2
author: windows-driver-content
description: The IDrmPort2 interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see Digital Rights Management).
old-location: audio\idrmport2.htm
old-project: audio
ms.assetid: c0fa64cf-bfc7-415c-a30d-50bf6182cc3d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcUnregisterIoTimeout
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
req.alt-api: IDrmPort2
req.alt-loc: portcls.h
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
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IDrmPort2 interface



## -description
The <code>IDrmPort2</code> interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see <a href="https://msdn.microsoft.com/7ce19196-5180-421f-b6be-ac4a235a8c16">Digital Rights Management</a>). The port driver implements this interface and exposes it to the miniport driver. The WaveCyclic and WavePci port drivers support this interface. To determine whether a port driver supports the <code>IDrmPort2</code> interface, a miniport driver calls the port (<a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536905">IPortWavePci</a>) object's <b>QueryInterface</b> method with REFIID <b>IID_IDrmPort2</b>. <code>IDrmPort2</code> inherits from the <a href="..\portcls\nn-portcls-idrmport.md">IDrmPort</a> interface.

The methods in this interface serve as alternate entry points to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536356">DRM functions</a> in the <a href="audio.kernel_mode_wdm_audio_components#drmk_system_driver#drmk_system_driver">DRMK system driver</a>, drmk.sys.

For more information about <code>IDrmPort2</code>, see <a href="https://msdn.microsoft.com/aee123e4-bc1b-4ba8-9f8d-a9d207297c8d">Content IDs and Content Rights</a>.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDrmPort2</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.


## -remarks
