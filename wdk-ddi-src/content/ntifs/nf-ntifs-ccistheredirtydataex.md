---
UID: NF.ntifs.CcIsThereDirtyDataEx
title: CcIsThereDirtyDataEx function
author: windows-driver-content
description: The CcIsThereDirtyDataEx routine determines whether a volume contains any files that have dirty data in the system cache.
old-location: ifsk\ccistheredirtydataex.htm
old-project: ifsk
ms.assetid: 88378f82-2975-4b53-9dde-53ab81df3c53
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: CcIsThereDirtyDataEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CcIsThereDirtyDataEx
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
req.irql: PASSIVE_LEVEL
---

# CcIsThereDirtyDataEx function



## -description
The <b>CcIsThereDirtyDataEx</b> routine determines whether a volume contains any files that have dirty data in the system cache.



## -syntax

````
BOOLEAN CcIsThereDirtyDataEx(
  _In_     PVPB   Vpb,
  _In_opt_ PULONG NumberOfDirtyPages
);
````


## -parameters

### -param Vpb [in]

A pointer to a volume parameter block (VPB) for the volume. 


### -param NumberOfDirtyPages [in, optional]

An optional pointer to an unsigned long buffer that receives the number of dirty pages on the volume (associated with the Vpb parameter). 


## -returns
The <b>CcIsThereDirtyDataEx</b> routine returns <b>TRUE</b> if the volume contains one or more cached files whose data has been modified in the cache, but not yet flushed to disk. Otherwise, this routine returns <b>FALSE</b>.


## -remarks
This routine will return <b>TRUE</b> if any dirty pages exist including temporary files (<a href="ifsk.ccistheredirtydata">CcIsThereDirtyData</a> ignores temporary files).  It will also return <b>TRUE</b> if there is any data currently queued to the volume.


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
Available in Windows Vista and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or FltKernel.h)</dt>
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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.ccflushcache">CcFlushCache</a>
</dt>
<dt>
<a href="ifsk.ccpurgecachesection">CcPurgeCacheSection</a>
</dt>
<dt>
<a href="ifsk.ccistheredirtydata">CcIsThereDirtyData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcIsThereDirtyDataEx routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

