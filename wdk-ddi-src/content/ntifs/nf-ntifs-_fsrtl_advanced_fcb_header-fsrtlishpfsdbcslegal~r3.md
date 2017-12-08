---
UID: NF.ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlIsHpfsDbcsLegal~r3
title: FsRtlIsHpfsDbcsLegal function
author: windows-driver-content
description: The FsRtlIsHpfsDbcsLegal routine determines whether the specified ANSI or double-byte character set (DBCS) string is a legal HPFS file name.
old-location: ifsk\fsrtlishpfsdbcslegal.htm
old-project: ifsk
ms.assetid: 44088ca7-4a10-4002-8ae8-edd228a903f2
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlIsHpfsDbcsLegal
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlIsHpfsDbcsLegal
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

# FsRtlIsHpfsDbcsLegal function



## -description
The <b>FsRtlIsHpfsDbcsLegal</b> routine determines whether the specified ANSI or double-byte character set (DBCS) string is a legal HPFS file name.


## -syntax

````
BOOLEAN FsRtlIsHpfsDbcsLegal(
  _In_ ANSI_STRING DbcsName,
  _In_ BOOLEAN     WildCardsPermissible,
  _In_ BOOLEAN     PathNamePermissible,
  _In_ BOOLEAN     LeadingBackslashPermissible
);
````


## -parameters

### -param DbcsName [in]

A pointer to the string to be tested.

### -param WildCardsPermissible [in]

Set to <b>TRUE</b> if wildcard characters are to be considered legal, <b>FALSE</b> otherwise.

### -param PathNamePermissible [in]

Set to <b>TRUE</b> if <i>DbcsName</i> can be a full pathname containing backslash characters, <b>FALSE</b> if it can only be a file name.

### -param LeadingBackslashPermissible [in]

Set to <b>TRUE</b> if a single leading backslash is permissible in the file or pathname, <b>FALSE</b> otherwise.

## -returns
The <b>FsRtlIsHpfsDbcsLegal</b> routine returns <b>TRUE</b> if the string is a legal HPFS file name, <b>FALSE</b> otherwise.

## -remarks
The <b>FsRtlIsHpfsDbcsLegal</b> routine determines whether the specified file name conforms to the HPFS-specific rules for legal file names. This routine will check the file name or, if <i>PathNamePermissible</i> is specified as <b>TRUE</b>, whether the whole pathname is a legal HPFS name.

HPFS file names must obey the following rules:

The following characters are illegal in HPFS file names: 0x0000 - 0x001F, " (quotation marks), / (slash), : (colon), &lt; (less-than sign), &gt; (greater-than sign), ? (question mark), | (vertical bar or pipe), * (asterisk)

An HPFS file name cannot end in a period or a space. For example, the files "foo " and "foo." are illegal, while ".foo", " foo" and "foo.bar.foo" are legal.

An HPFS file name can contain no more than 255 bytes.

HPFS file names are case-preserving, but not case insensitive. Lowercase file names are not automatically converted to uppercase. However, case is ignored in file name comparisons.

For information about other string-handling routines, see <a href="kernel.strings">Strings</a>. 

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
This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems. 
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include FltKernel.h or Ntifs.h)</dt>
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
<a href="kernel.ansi_string">ANSI_STRING</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsHpfsDbcsLegal routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
