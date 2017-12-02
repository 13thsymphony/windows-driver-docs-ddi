---
UID: NN.portcls.IDrmPort
title: IDrmPort
author: windows-driver-content
description: The IDrmPort interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see Digital Rights Management).
old-location: audio\idrmport.htm
old-project: audio
ms.assetid: 3a4b9bf7-74cc-409f-9b63-db61d7c977cd
ms.author: windowsdriverdev
ms.date: 11/28/2017
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
req.alt-api: IDrmPort
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
req.iface: 
---

# IDrmPort interface



## -description
<p>The <code>IDrmPort</code> interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see <a href="https://msdn.microsoft.com/7ce19196-5180-421f-b6be-ac4a235a8c16">Digital Rights Management</a>). The port driver implements this interface and exposes it to the miniport driver. In Windows XP and later, the WaveCyclic and WavePci port drivers support this interface. To determine whether a port driver supports the <code>IDrmPort</code> interface, a miniport driver calls the port (<a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a> or <a href="audio.iportwavepci">IPortWavePci</a>) object's <b>QueryInterface</b> method with REFIID <b>IID_IDrmPort</b>. </p>
<p>The methods in this interface serve as alternate entry points to the <a href="audio.drm_functions">DRM Functions</a> in the <a href="audio.kernel_mode_wdm_audio_components#drmk_system_driver#drmk_system_driver">DRMK system driver</a>, drmk.sys.</p>
<p>For more information about <code>IDrmPort</code>, see <a href="https://msdn.microsoft.com/aee123e4-bc1b-4ba8-9f8d-a9d207297c8d">Content IDs and Content Rights</a>.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDrmPort</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
</table>