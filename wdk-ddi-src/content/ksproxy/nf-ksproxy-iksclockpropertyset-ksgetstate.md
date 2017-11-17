---
UID: NF.ksproxy.IKsClockPropertySet.KsGetState
title: IKsClockPropertySet::KsGetState
author: windows-driver-content
description: The KsGetState method retrieves the streaming state of a pin from the underlying clock.
old-location: stream\iksclockpropertyset_ksgetstate.htm
ms.assetid: 153e4f47-ae07-4f1e-9ab5-69ef6565ad5d
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: stream
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsClockPropertySet.KsGetState
req.alt-loc: ksproxy.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
ms.keywords: IKsClockPropertySet, KsGetState, IKsClockPropertySet::KsGetState
req.iface: IKsClockPropertySet
---

# IKsClockPropertySet::KsGetState method



## -description
<p>The <b>KsGetState</b> method retrieves the streaming state of a pin from the underlying clock.</p>


## -syntax

````
HRESULT KsGetState(
  [out] KSSTATE *State
);
````


## -parameters
<dl>

### -param <i>State</i> [out]

<dd>
<p>Pointer to a variable that receives a value that specifies the streaming state of a pin. This value can be one of the following values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a> enumerated type:</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>KSSTATE_STOP</p>
</td>
<td>
<p>The streaming of data to or from the pin is stopped. Represents the initial state of the pin with the least resource usage and the most latency to obtain a <b>KSSTATE_RUN</b> state. </p>
</td>
</tr>
<tr>
<td>
<p>KSSTATE_ACQUIRE</p>
</td>
<td>
<p>Represents the state at which allocators are negotiated and resources acquired, though no data may be buffered in this state.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTATE_PAUSE</p>
</td>
<td>
<p>The clock is waiting and is prepared to instantly change to the <b>KSSTATE_RUN</b> state. Represents the mode of most resource usage and least latency to a Run state, without actually being in a <b>KSSTATE_RUN</b> state. Data can be buffered in this state. If the state of the pin is queried and that state is currently paused, the pin can return an error of STATUS_NO_DATA_DETECTED to indicate that this pin does not perform queuing of data when in a paused state.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTATE_RUN</p>
</td>
<td>
<p>The pin is streaming data. That is, the pin consumes or produces stream data.</p>
</td>
</tr>
</table>
<p> </p>
</dd>
</dl>

## -returns
<p>Returns NOERROR if successful; otherwise, returns an error code.</p>

## -remarks
<p>The state of the pin gives gross motor control for pins. Fine motor control is done on a class-by-class basis with custom properties. For instance, in order to make an external laser disc player spin up, you could set a custom Mode property specific to that class. Setting this property may also change the state of the device, though not necessarily, depending on the effect of the mode.</p>

<p>A filter itself can support this state property so that applications can set the entire filter's state. Otherwise, each pin must have its state set. When the state of a pin transitions from KSSTATE_STOP, each connection that forwards IRPs must recalculate stack depth.</p>

<p>The proxy uses the KSPROPERTY_CLOCK_STATE property to retrieve the streaming state of a pin. </p>

<p>The state of the pin gives gross motor control for pins. Fine motor control is done on a class-by-class basis with custom properties. For instance, in order to make an external laser disc player spin up, you could set a custom Mode property specific to that class. Setting this property may also change the state of the device, though not necessarily, depending on the effect of the mode.</p>

<p>A filter itself can support this state property so that applications can set the entire filter's state. Otherwise, each pin must have its state set. When the state of a pin transitions from KSSTATE_STOP, each connection that forwards IRPs must recalculate stack depth.</p>

<p>The proxy uses the KSPROPERTY_CLOCK_STATE property to retrieve the streaming state of a pin. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksproxy.h (include Ksproxy.h)</dt>
</dl>
</td>
</tr>
</table>