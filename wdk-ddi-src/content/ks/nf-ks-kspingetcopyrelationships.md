---
UID: NF.ks.KsPinGetCopyRelationships
title: KsPinGetCopyRelationships function
author: windows-driver-content
description: The KsPinGetCopyRelationships function returns copy relationship information for a pin that is contained within a pin-centric filter.
old-location: stream\kspingetcopyrelationships.htm
old-project: stream
ms.assetid: 7f74cbf1-2382-471c-ab07-fdb7e615cb0b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsPinGetCopyRelationships
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsPinGetCopyRelationships
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
---

# KsPinGetCopyRelationships function



## -description
The <b>KsPinGetCopyRelationships</b> function returns copy relationship information for a pin that is contained within a <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">pin-centric</a> filter.


## -syntax

````
void KsPinGetCopyRelationships(
  _In_  PKSPIN Pin,
  _Out_ PKSPIN *CopySource,
  _Out_ PKSPIN *DelegateBranch
);
````


## -parameters

### -param Pin [in]

A pointer to the <a href="stream.kspin">KSPIN</a> structure from which you want to acquire copy information.

### -param CopySource [out]

A pointer to a pointer to a <a href="stream.kspin">KSPIN</a> structure that is the copy source for <i>Pin</i>. If <i>Pin</i> is the copy source, AVStream sets this parameter to <b>NULL</b>.

### -param DelegateBranch [out]

A pointer to a pointer to a <a href="stream.kspin">KSPIN</a> structure that is the pin from which <i>Pin</i> receives delegated frames. If <i>Pin</i> is the delegator, AVStream sets this parameter to <b>NULL</b>.

## -returns
None

## -remarks

<a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-centric</a> filters receive similar <i>CopySource</i> and <i>DelegateBranch</i> information when AVStream calls the minidriver's <a href="stream.avstrminifilterprocess">AVStrMiniFilterProcess</a> function with an array of <a href="stream.ksprocesspin_indexentry">KSPROCESSPIN_INDEXENTRY</a> structures.

The only difference is that <b>KsPinGetCopyRelationships</b> returns pointers to PKSPIN rather than pointers to PKSPROCESSPIN. For more information about the <i>CopySource</i> and <i>DelegateBranch</i> parameters, see <a href="https://msdn.microsoft.com/c2cfc183-0f4c-4104-a580-234e0483eee4">AVStream Splitters</a>.

All pins operate independently in the context of a pin-centric filter. As a result, a minidriver that calls <b>KsPinGetCopyRelationships</b> is responsible for ensuring that the appropriate synchronization is performed before call time.

To guarantee safety when calling <b>KsPinGetCopyRelationships</b>, either obtain the control mutex (do not use this mechanism in a processing dispatch) or make sure that the pin does not transition below <b>KSSTATE_PAUSE</b> while calling or using the information obtained. For more information about mutexes, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

For more information, see <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a> and <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>
</dt>
<dt>
<a href="stream.ksprocesspin">KSPROCESSPIN</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetCopyRelationships function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
