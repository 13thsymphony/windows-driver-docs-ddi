---
UID: NF:ntifs.CcUnpinRepinnedBcb
title: CcUnpinRepinnedBcb function
author: windows-driver-content
description: The CcUnpinRepinnedBcb routine unpins a repinned buffer control block (BCB).
old-location: ifsk\ccunpinrepinnedbcb.htm
old-project: ifsk
ms.assetid: 96a35574-87dc-4a2f-aaef-616096839f3f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: CcUnpinRepinnedBcb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CcUnpinRepinnedBcb
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
req.typenames: TOKEN_TYPE
---

# CcUnpinRepinnedBcb function



## -description
The <b>CcUnpinRepinnedBcb</b> routine unpins a repinned buffer control block (BCB).



## -syntax

````
VOID CcUnpinRepinnedBcb(
  _In_  PVOID            Bcb,
  _In_  BOOLEAN          WriteThrough,
  _Out_ PIO_STATUS_BLOCK IoStatus
);
````


## -parameters

### -param Bcb [in]

Pointer to the repinned BCB.


### -param WriteThrough [in]

Set to <b>TRUE</b> if the BCB should be written through.


### -param IoStatus [out]

Pointer to an IO_STATUS_BLOCK structure. If the call to <b>CcUnpinRepinnedBcb</b> succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that were successfully flushed to disk.


## -returns
None


## -remarks
File systems call <b>CcUnpinRepinnedBcb</b> to write a previously pinned buffer through to disk.

Every call to <a href="..\ntifs\nf-ntifs-ccrepinbcb.md">CcRepinBcb</a> must be matched by a subsequent call to <b>CcUnpinRepinnedBcb</b>.

Because <b>CcUnpinRepinnedBcb</b> acquires the BCB resource exclusively, the caller must be extremely careful to avoid deadlocks. If possible, the caller should own no resources. Otherwise the caller must guarantee that it has nothing else pinned in the same cached file. Normally <b>CcUnpinRepinnedBcb</b> is called during request completion, after all other resources have been released.

<b>CcUnpinRepinnedBcb</b> synchronously writes the buffer (for write-through requests) and unpins the BCB repinned by the earlier call to <a href="..\ntifs\nf-ntifs-ccrepinbcb.md">CcRepinBcb</a>.


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
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-ccrepinbcb.md">CcRepinBcb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcUnpinRepinnedBcb routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

