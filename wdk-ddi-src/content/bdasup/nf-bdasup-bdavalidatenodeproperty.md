---
UID: NF.bdasup.BdaValidateNodeProperty
title: BdaValidateNodeProperty
author: windows-driver-content
description: The BdaValidateNodeProperty function validates that a node property request is associated with a specific pin.
old-location: stream\bdavalidatenodeproperty.htm
old-project: stream
ms.assetid: e3a6d757-68c5-49d1-92cc-0ebf6ba6bbec
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: BdaValidateNodeProperty
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
req.alt-api: BdaValidateNodeProperty
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

# BdaValidateNodeProperty function



## -description
<p>The <b>BdaValidateNodeProperty</b> function validates that a node property request is associated with a specific pin. </p>


## -syntax

````
NTSTATUS BdaValidateNodeProperty(
  _In_ PIRP        Irp,
  _In_ PKSPROPERTY pKSProperty
);
````


## -parameters
<dl>

### -param Irp [in]

<dd>
<p>Points to the IRP for the request to validate that the current pin controls the node property at <i>pKSProperty</i>. The BDA minidriver can receive this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564355">KSPROPERTY_BDA_RF_TUNER_FREQUENCY</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff564286">KSPROPERTY_BDA_AUTODEMODULATE_START</a> request.</p>
</dd>

### -param pKSProperty [in]

<dd>
<p>Points to a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property and request type of the property request.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS or an appropriate error code. </p>

## -remarks
<p>A pin method in a BDA minidriver calls the <b>BdaValidateNodeProperty</b> function to validate that the pin controls a specific node property after the minidriver receives the node property request from the network provider. This node property request can be, for example, a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564355">KSPROPERTY_BDA_RF_TUNER_FREQUENCY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566542">KSPROPSETID_BdaFrequencyFilter</a> property set or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564286">KSPROPERTY_BDA_AUTODEMODULATE_START</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566533">KSPROPSETID_BdaAutodemodulate</a> property set. These property sets manipulate tuner and demodulator nodes. After successfully calling <b>BdaValidateNodeProperty</b>, the minidriver obtains a pointer to the BDA filter from the passed IRP so that the minidriver can perform an operation on the particular node. </p>

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
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564286">KSPROPERTY_BDA_AUTODEMODULATE_START</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564355">KSPROPERTY_BDA_RF_TUNER_FREQUENCY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566533">KSPROPSETID_BdaAutodemodulate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566542">KSPROPSETID_BdaFrequencyFilter</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaValidateNodeProperty function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
