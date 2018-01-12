---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlFindInTunnelCache~r6
title: FsRtlFindInTunnelCache function
author: windows-driver-content
description: The FsRtlFindInTunnelCache routine searches for a matching entry in the tunnel cache that matches the specified name.
old-location: ifsk\fsrtlfindintunnelcache.htm
old-project: ifsk
ms.assetid: 80c24c5b-49a3-4ecc-92fe-3477cbb8a544
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlFindInTunnelCache
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
req.alt-api: FsRtlFindInTunnelCache
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
req.typenames: TOKEN_TYPE
---

# FsRtlFindInTunnelCache function



## -description
The <b>FsRtlFindInTunnelCache</b> routine searches for a matching entry in the tunnel cache that matches the specified name.



## -syntax

````
BOOLEAN FsRtlFindInTunnelCache(
  _In_    TUNNEL         *Cache,
  _In_    ULONGLONG      DirKey,
  _In_    UNICODE_STRING *Name,
  _Out_   UNICODE_STRING *ShortName,
  _Out_   UNICODE_STRING *LongName,
  _Inout_ ULONG          *DataLength,
  _Out_   VOID           *Data
);
````


## -parameters

### -param Cache [in]

Pointer to a tunnel cache initialized by <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache.md">FsRtlInitializeTunnelCache</a>.


### -param DirKey [in]

Key value of the directory containing the file that is being created or renamed.


### -param Name [in]

Pointer to a Unicode string containing the new name for the file that is being renamed or created.


### -param ShortName [out]

Pointer to a caller-allocated Unicode string to receive the short name of the tunneled file. This string must be long enough to hold a full 8.3 file name. (Unlike <i>LongName</i>, <i>ShortName</i> is not grown dynamically.)


### -param LongName [out]

Pointer to a caller-allocated Unicode string to receive the long name of the tunneled file. If this string is not large enough to hold the tunneled name, <b>FsRtlFindInTunnelCache</b> replaces it with a larger system-allocated string. If such a string is allocated, the caller is responsible for detecting this case and freeing the new system-allocated string as well as the original caller-allocated string.


### -param DataLength [in, out]

On input, this is a pointer to a variable that specifies the length of the buffer pointed to by <i>Data</i>. On output, the same variable receives the length in bytes of the data written to the buffer.


### -param Data [out]

Pointer to a caller-allocated buffer to receive the data found in the tunnel cache. 


## -returns
<b>FsRtlFindInTunnelCache</b> returns <b>TRUE</b> if a matching entry is found in the tunnel cache, <b>FALSE</b> otherwise.


## -remarks
File systems can call <b>FsRtlFindInTunnelCache</b> when a file name is added to a directory for a file that is being created or renamed. <b>FsRtlFindInTunnelCache</b> searches the tunnel cache for an entry that matches <i>DirKey</i> and <i>Name</i>. If one is found, <b>FsRtlFindInTunnelCache</b> fetches the cached information.

The match is performed as follows:

The value of <i>DirKey</i> is compared against the entry's directory key. (This is the <i>DirectoryKey</i> value that was passed to <b>FsRtlAddToTunnelCache</b>.)

If <i>KeyByShortName</i> was set to <b>TRUE</b> in the call to <b>FsRtlAddToTunnelCache</b>, the string pointed to by <i>Name</i> is compared against the short name of the tunneled file. Otherwise, it is compared against the long name.

The value of the buffer length variable pointed to by <i>DataLength</i> must be greater than or equal to the length in bytes of the data stored in the tunnel cache entry.

The caller is required to synchronize this call against <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletetunnelcache.md">FsRtlDeleteTunnelCache</a>. In other words, a file system must ensure that it does not call <b>FsRtlFindInTunnelCache</b> and <b>FsRtlDeleteTunnelCache</b> at the same time from different threads. 

For more information about file name tunneling, see <a href="http://go.microsoft.com/fwlink/p/?linkid=3100&amp;amp;id=172190">Microsoft Knowledge Base Article 172190</a>.


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
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletetunnelcache.md">FsRtlDeleteTunnelCache</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache.md">FsRtlInitializeTunnelCache</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlFindInTunnelCache routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

