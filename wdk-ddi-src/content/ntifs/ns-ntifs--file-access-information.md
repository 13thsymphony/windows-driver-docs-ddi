---
UID: NS.ntifs._FILE_ACCESS_INFORMATION
title: FILE_ACCESS_INFORMATION
author: windows-driver-content
description: The FILE_ACCESS_INFORMATION structure is used to query for or set the access rights of a file.
old-location: kernel\file_access_information.htm
old-project: kernel
ms.assetid: f5a09843-caf7-4550-bbc6-c0d799d66cd6
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: FILE_ACCESS_INFORMATION, FILE_ACCESS_INFORMATION, *PFILE_ACCESS_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_ACCESS_INFORMATION
req.alt-loc: Ntifs.h
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

# FILE_ACCESS_INFORMATION structure



## -description
<p>The <b>FILE_ACCESS_INFORMATION</b> structure is used to query for or set the access rights of a file.</p>


## -syntax

````
typedef struct _FILE_ACCESS_INFORMATION {
  ACCESS_MASK AccessFlags;
} FILE_ACCESS_INFORMATION, *PFILE_ACCESS_INFORMATION;
````


## -struct-fields
<dl>

### -field <b>AccessFlags</b>

<dd>
<p>Flags that specify a set of access rights in the access mask of an access control entry. This member is a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> routine.</p>

<p>The <i>AccessFlags</i> parameter is an access mask that encodes the user rights to a file object. An access mask can be used to encode the rights to an object that is assigned to a user or a user group, or to encode the requested access when a user opens an object. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows XP and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_ACCESS_INFORMATION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
