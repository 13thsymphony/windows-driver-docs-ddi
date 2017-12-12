---
UID: NF.ntifs.RtlInitializeUnicodePrefix
title: RtlInitializeUnicodePrefix function
author: windows-driver-content
description: The RtlInitializeUnicodePrefix routine initializes a prefix table.
old-location: ifsk\rtlinitializeunicodeprefix.htm
old-project: ifsk
ms.assetid: 8891641a-392c-4c2b-aa5a-9464774d8610
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlInitializeUnicodePrefix
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlInitializeUnicodePrefix
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
req.irql: < DISPATCH_LEVEL
---

# RtlInitializeUnicodePrefix function



## -description
The <b>RtlInitializeUnicodePrefix</b> routine initializes a prefix table.



## -syntax

````
VOID RtlInitializeUnicodePrefix(
  _Out_ PUNICODE_PREFIX_TABLE PrefixTable
);
````


## -parameters

### -param PrefixTable [out]

Pointer to caller-allocated buffer, which must be at least <b>sizeof</b>(UNICODE_PREFIX_TABLE), for the prefix table header. <b>RtlInitializeUnicodePrefix</b> initializes this header, which should be considered opaque by the caller. 


## -returns
None


## -remarks
File systems must call <b>RtlInitializeUnicodePrefix</b> to initialize the prefix table before using any other <b>Rtl..UnicodePrefix</b> routines on it. The initialized prefix table structure should be considered opaque.

Callers of the <b>Rtl..UnicodePrefix</b> routines are responsible for synchronizing access to the prefix table. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

For information about other string-handling routines, see <a href="kernel.strings">Strings</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows XP

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2003

</td>
</tr>
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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt; DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exinitializefastmutex">ExInitializeFastMutex</a>
</dt>
<dt>
<a href="ifsk.rtlfindunicodeprefix">RtlFindUnicodePrefix</a>
</dt>
<dt>
<a href="ifsk.rtlinsertunicodeprefix">RtlInsertUnicodePrefix</a>
</dt>
<dt>
<a href="ifsk.rtlnextunicodeprefix">RtlNextUnicodePrefix</a>
</dt>
<dt>
<a href="ifsk.rtlremoveunicodeprefix">RtlRemoveUnicodePrefix</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlInitializeUnicodePrefix routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

