---
UID: NF.ntifs.CcGetFileObjectFromBcb
title: CcGetFileObjectFromBcb
author: windows-driver-content
description: Given a pointer to a pinned buffer control block (BCB) for a file, the CcGetFileObjectFromBcb routine returns a pointer to the file object that the cache manager is using for that file.
old-location: ifsk\ccgetfileobjectfrombcb.htm
old-project: ifsk
ms.assetid: d30a2ee4-4736-4127-95db-b86e782c3577
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: CcGetFileObjectFromBcb
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
req.alt-api: CcGetFileObjectFromBcb
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
req.iface: 
---

# CcGetFileObjectFromBcb function



## -description
<p>Given a pointer to a pinned buffer control block (BCB) for a file, the <b>CcGetFileObjectFromBcb</b> routine returns a pointer to the file object that the cache manager is using for that file.</p>


## -syntax

````
PFILE_OBJECT CcGetFileObjectFromBcb(
  _In_ PVOID Bcb
);
````


## -parameters
<dl>

### -param <i>Bcb</i> [in]

<dd>
<p>Pointer to the pinned BCB.</p>
</dd>
</dl>

## -returns
<p>Pointer to the file object, or <b>NULL</b> if the file is not cached or is no longer cached.</p>

## -remarks
<p>The file object pointer is guaranteed to remain valid as long as the BCB exists.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
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
<a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcGetFileObjectFromBcb routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
