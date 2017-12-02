---
UID: NF.bdasup.BdaGetChangeState
title: BdaGetChangeState
author: windows-driver-content
description: The BdaGetChangeState function returns the current change state of BDA topology.
old-location: stream\bdagetchangestate.htm
old-project: stream
ms.assetid: fd111e80-fc3e-4f21-97cb-1f75ae34d1e9
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: BdaGetChangeState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BdaGetChangeState
req.alt-loc: Bdasup.lib,Bdasup.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# BdaGetChangeState function



## -description
<p>The <b>BdaGetChangeState</b> function returns the current change state of BDA topology. </p>


## -syntax

````
NTSTATUS BdaGetChangeState(
  _In_      PIRP              Irp,
  _Out_opt_ PBDA_CHANGE_STATE pChangeState
);
````


## -parameters
<dl>

### -param Irp [in]

<dd>
<p>Points to the IRP for the request to get the current change state. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563417">KSMETHOD_BDA_GET_CHANGE_STATE</a> request.</p>
</dd>

### -param pChangeState [out, optional]

<dd>
<p>Points to a variable that receives the current change state of BDA topology. The BDA change state can be one of the following values from the <a href="stream.bda_change_state">BDA_CHANGE_STATE</a> enumerated type:</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>BDA_CHANGES_COMPLETE</p>
</td>
<td>
<p>BDA topology changes are complete. </p>
</td>
</tr>
<tr>
<td>
<p>BDA_CHANGES_PENDING</p>
</td>
<td>
<p>BDA topology changes are pending.</p>
</td>
</tr>
</table>
<p> </p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS or an appropriate error code. </p>

## -remarks
<p>A BDA minidriver calls the <b>BdaGetChangeState</b> function to retrieve the current change state of BDA topology after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563417">KSMETHOD_BDA_GET_CHANGE_STATE</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563403">KSMETHODSETID_BdaChangeSync</a> method set from the network provider. BDA minidrivers define dispatch and filter-automation tables so that those minidrivers either dispatch the <b>BdaGetChangeState</b> function directly or intercept this request using an internal method (<a href="stream.kstrmethodhandler">KStrMethodHandler</a>), which then calls the <b>BdaGetChangeState</b> function. For example, BDA minidrivers that intercept this request can obtain a pointer to the BDA filter from the passed IRP so that they can: </p>

<p>Not only check for pending topology changes but also for pending changes on the filter. </p>

<p>Return the current change state for both BDA topology and the BDA filter. </p>

<p>See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/1833864a-5759-437c-ba60-0b38602d9e41">Changing BDA Filter Properties</a> for more information. </p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Bdasup.h (include Bdasup.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Bdasup.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.bda_change_state">BDA_CHANGE_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563417">KSMETHOD_BDA_GET_CHANGE_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563403">KSMETHODSETID_BdaChangeSync</a>
</dt>
<dt>
<a href="stream.kstrmethodhandler">KStrMethodHandler</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaGetChangeState function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
