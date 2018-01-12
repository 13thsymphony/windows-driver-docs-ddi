---
UID: NF:portcls.IPortWavePciStream.ReleaseMapping
title: IPortWavePciStream::ReleaseMapping method
author: windows-driver-content
description: The ReleaseMapping method releases a mapping that was obtained by a previous call to IPortWavePciStream::GetMapping.
old-location: audio\iportwavepcistream_releasemapping.htm
old-project: audio
ms.assetid: c4464fba-cc23-47d2-87d6-82b3eba8ddbe
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortWavePciStream, IPortWavePciStream::ReleaseMapping, ReleaseMapping
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortWavePciStream.ReleaseMapping
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
req.irql: <=DISPATCH_LEVEL
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IPortWavePciStream::ReleaseMapping method



## -description
The <code>ReleaseMapping</code> method releases a mapping that was obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536909">IPortWavePciStream::GetMapping</a>.



## -syntax

````
NTSTATUS ReleaseMapping(
  [in] PVOID Tag
);
````


## -parameters

### -param Tag [in]

Specifies a tag value identifying the mapping that is to be released. For more information, see the following Remarks section.


## -returns
<code>ReleaseMapping</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.


## -remarks
Set the <i>Tag</i> parameter to the same tag value that you used to identify the mapping in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536909">IPortWavePciStream::GetMapping</a> that originally obtained the mapping.

The miniport driver must keep track of the order in which it acquires its mappings from calls to <b>IPortWavePciStream::GetMapping</b>, and it must release the mappings in the same order.

To avoid potential deadlocks, the miniport driver must avoid holding a spin lock during its call to <code>ReleaseMapping</code>. See the ac97 sample audio driver in the Microsoft Windows Driver Kit (WDK) for a code example that uses a spin lock to serialize accesses to shared data structures and peripherals in a multiprocessor system. The sample code calls <a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a> before calling <code>ReleaseMapping</code> and calls <a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a> after calling <code>ReleaseMapping</code>. Between the calls to release and acquire the spin lock, the driver thread must not assume that it has exclusive access to the data or peripherals that are guarded by the spin lock. The Driver Verifier tool (see the description of this tool at the <a href="http://go.microsoft.com/fwlink/p/?linkid=8753">Driver Verifier</a> website) checks for active spin locks during calls to <code>ReleaseMapping</code>; if it detects one, it generates a 0xC4 (deadlock detection) bug check.


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
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iportwavepcistream.md">IPortWavePciStream</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536909">IPortWavePciStream::GetMapping</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536730">IMiniportWavePciStream::RevokeMappings</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWavePciStream::ReleaseMapping method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

