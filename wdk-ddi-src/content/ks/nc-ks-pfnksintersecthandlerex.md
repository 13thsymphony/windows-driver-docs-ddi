---
UID: NC.ks.PFNKSINTERSECTHANDLEREX
title: PFNKSINTERSECTHANDLEREX
author: windows-driver-content
description: AVStream calls a minidriver's AVStrMiniIntersectHandlerEx routine to determine the highest quality intersection of two data ranges.
old-location: stream\avstrminiintersecthandlerex.htm
old-project: stream
ms.assetid: d80f8bc6-29dc-4cb0-87f5-414ec6418156
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVStrMiniIntersectHandlerEx
req.alt-loc: ks.h
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
req.iface: 
---

# PFNKSINTERSECTHANDLEREX callback



## -description
<p>AVStream calls a minidriver's <i>AVStrMiniIntersectHandlerEx</i> routine to determine the highest quality intersection of two data ranges.</p>


## -prototype

````
PFNKSINTERSECTHANDLEREX AVStrMiniIntersectHandlerEx;

NTSTATUS AVStrMiniIntersectHandlerEx(
  _In_  PVOID        Context,
  _In_  PIRP         Irp,
  _In_  PKSP_PIN     Pin,
  _In_  PKSDATARANGE DataRange,
  _In_  PKSDATARANGE MatchingDataRange,
  _In_  ULONG        DataBufferSize,
  _Out_ PVOID        Data,
  _Out_ PULONG       DataSize
)
{ ... }
````


## -parameters
<dl>

### -param Context [in]

<dd>
<p>Pointer to the <b>Context</b> member of the corresponding <a href="..\ks\ns-ks--ksfilter.md">KSFILTER</a> structure.</p>
</dd>

### -param Irp [in]

<dd>
<p>Pointer to the <a href="..\wdm\ns-wdm--irp.md">IRP</a> containing the intersection request.</p>
</dd>

### -param Pin [in]

<dd>
<p>Pointer to a structure of type <a href="stream.ksp_pin">KSP_PIN</a> that was passed in the intersection property request.</p>
</dd>

### -param DataRange [in]

<dd>
<p>Pointer to an array of <a href="stream.ksdatarange">KSDATARANGE</a> structures.</p>
</dd>

### -param MatchingDataRange [in]

<dd>
<p>Pointer to an array of <a href="stream.ksdatarange">KSDATARANGE</a> structures to match to <i>DataRange</i>.</p>
</dd>

### -param DataBufferSize [in]

<dd>
<p>Specifies a value of type ULONG that contains the size of the data buffer.</p>
</dd>

### -param Data [out]

<dd>
<p>Pointer to an optional data buffer in which the minidriver outputs the intersection.</p>
</dd>

### -param DataSize [out]

<dd>
<p>Pointer to a value of type ULONG specifying the size of the data buffer.</p>
</dd>
</dl>

## -returns
<p>If the callback finds a match, return STATUS_SUCCESS. Otherwise return STATUS_NO_MATCH.</p>

## -remarks
<p>The minidriver specifies this routine's address in the <b>IntersectHandler</b> member of a <a href="..\ks\ns-ks--kspin-descriptor-ex.md">KSPIN_DESCRIPTOR_EX</a> structure.</p>

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
<dt>Ks.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks--ksfilter.md">KSFILTER</a>
</dt>
<dt>
<a href="stream.ksp_pin">KSP_PIN</a>
</dt>
<dt>
<a href="stream.ksdatarange">KSDATARANGE</a>
</dt>
<dt>
<a href="..\ks\ns-ks--kspin-descriptor-ex.md">KSPIN_DESCRIPTOR_EX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565198">KSPROPERTY_PIN_DATAINTERSECTION</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspindataintersectionex.md">KsPinDataIntersectionEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVStrMiniIntersectHandlerEx routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
