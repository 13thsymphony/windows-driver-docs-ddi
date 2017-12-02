---
UID: NF.bdasup.BdaCreateTopology
title: BdaCreateTopology
author: windows-driver-content
description: The BdaCreateTopology function creates the topology between two pins.
old-location: stream\bdacreatetopology.htm
old-project: stream
ms.assetid: 855ef77c-2a85-4c8c-b8e3-c4aaa0d2a089
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: BdaCreateTopology
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
req.alt-api: BdaCreateTopology
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

# BdaCreateTopology function



## -description
<p>The <b>BdaCreateTopology</b> function creates the topology between two pins. </p>


## -syntax

````
NTSTATUS BdaCreateTopology(
  _In_ PKSFILTER pKSFilter,
  _In_ ULONG     InputPinId,
  _In_ ULONG     OutputPinId
);
````


## -parameters
<dl>

### -param pKSFilter [in]

<dd>
<p>Points to the BDA filter on which to create topology.</p>
</dd>

### -param InputPinId [in]

<dd>
<p>Specifies the identifier of the filter's input pin.</p>
</dd>

### -param OutputPinId [in]

<dd>
<p>Specifies the identifier of the filter's output pin.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS or an appropriate error code. Returns <b>NULL</b> if no valid pin pairing exists with the specified input and output pins. 

</p>

## -remarks
<p>A BDA minidriver calls the <a href="..\bdasup\nf-bdasup-bdamethodcreatetopology.md">BdaMethodCreateTopology</a> function when the network provider dynamically creates a topology between filter pins using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563413">KSMETHOD_BDA_CREATE_TOPOLOGY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set. If a BDA minidriver must create a topology between filter pins without relying on the network provider, the BDA minidriver should call the <b>BdaCreateTopology</b> function directly.</p>

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
<a href="..\bdasup\nf-bdasup-bdamethodcreatetopology.md">BdaMethodCreateTopology</a>
</dt>
<dt>
<a href="..\ks\ns-ks--ksfilter.md">KSFILTER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563413">KSMETHOD_BDA_CREATE_TOPOLOGY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaCreateTopology function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
