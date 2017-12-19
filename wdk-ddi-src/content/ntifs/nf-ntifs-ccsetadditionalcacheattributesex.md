---
UID: NF.ntifs.CcSetAdditionalCacheAttributesEx
title: CcSetAdditionalCacheAttributesEx function
author: windows-driver-content
description: Call the CcSetAdditionalCacheAttributesEx routine to enable extended cache behavior on a cached file.
old-location: ifsk\ccsetadditionalcacheattributesex.htm
old-project: ifsk
ms.assetid: 187719CD-5F0C-4AFD-BC00-ECD3C29A118F
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: CcSetAdditionalCacheAttributesEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CcSetAdditionalCacheAttributesEx
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
req.irql: <= APC_LEVEL
---

# CcSetAdditionalCacheAttributesEx function



## -description
Call the <b>CcSetAdditionalCacheAttributesEx</b> routine to enable extended cache behavior on a cached file.



## -syntax

````
VOID CcSetAdditionalCacheAttributesEx(
  _In_ PFILE_OBJECT FileObject,
  _In_ ULONG        Flags
);
````


## -parameters

### -param FileObject [in]

Pointer to a file object for the cached file.


### -param Flags [in]

Behavior flags to set for <i>FileObject</i>. Currently, only the  <b>AGGRESSIVE_UNMAP_BEHIND</b> flag is available. Setting this flag will allow the cache manager to optimize memory usage when modified writes are disabled for a file object.


## -returns
None


## -remarks
<b>CcSetAdditionalCacheAttributesEx</b> can be called any time after calling <a href="ifsk.ccinitializecachemap">CcInitializeCacheMap</a>. 


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
Available starting with Windows 8.

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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.ccsetadditionalcacheattributes">CcSetAdditionalCacheAttributes</a>
</dt>
<dt>
<a href="ifsk.ccinitializecachemap">CcInitializeCacheMap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcSetAdditionalCacheAttributesEx routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

