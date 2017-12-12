---
UID: NN.portcls.IPortClsRuntimePower
title: IPortClsRuntimePower
author: windows-driver-content
description: IPortClsRuntimePower is the interface that the port class driver (PortCls) uses for accessing the runtime power management capabilities of the audio adapter.
old-location: audio\iportclsruntimepower.htm
old-project: audio
ms.assetid: 8D03B2A0-6C8C-4EBE-86F4-70C8DE179947
ms.author: windowsdriverdev
ms.date: 12/6/2017
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
req.alt-api: IPortClsRuntimePower
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
---

# IPortClsRuntimePower interface



## -description
IPortClsRuntimePower is the interface that the port class driver (PortCls)  uses for accessing the runtime power management capabilities of the audio adapter.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortClsRuntimePower</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPortClsRuntimePower</b> also has these types of members:

The <b>IPortClsRuntimePower</b> interface has these methods.

The port class driver (PortCls) uses the <code>RegisterPowerControlCallback</code>  method to register a power control callback.

The port class driver (PortCls) uses the <code>SendPowerControl</code>  method to send power control codes to the audio adapter.

The port class driver (PortCls) uses the <code>UnregisterPowerControlCallback</code>  method to unregister a power control callback.

 


## -members
The <b>IPortClsRuntimePower</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="audio.iportclsruntimepower_registerpowercontrolcallback">RegisterPowerControlCallback</a>
</td>
<td align="left" width="63%">
The port class driver (PortCls) uses the <code>RegisterPowerControlCallback</code>  method to register a power control callback.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="audio.iportclsruntimepower_sendpowercontrol">SendPowerControl</a>
</td>
<td align="left" width="63%">
The port class driver (PortCls) uses the <code>SendPowerControl</code>  method to send power control codes to the audio adapter.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="audio.iportclsruntimepower_unregisterpowercontrolcallback">UnregisterPowerControlCallback</a>
</td>
<td align="left" width="63%">
The port class driver (PortCls) uses the <code>UnregisterPowerControlCallback</code>  method to unregister a power control callback.

</td>
</tr>
</table>The port class driver (PortCls) uses the <code>RegisterPowerControlCallback</code>  method to register a power control callback.

The port class driver (PortCls) uses the <code>SendPowerControl</code>  method to send power control codes to the audio adapter.

The port class driver (PortCls) uses the <code>UnregisterPowerControlCallback</code>  method to unregister a power control callback.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
</table>