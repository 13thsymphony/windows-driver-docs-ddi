---
UID: NS.ntddk._FILE_DISPOSITION_INFORMATION_EX
title: FILE_DISPOSITION_INFORMATION_EX
author: windows-driver-content
description: The FILE_DISPOSITION_INFORMATION_EX structure is used as an argument to the ZwSetInformationFileEx routine and indicates how the operating system should delete a file.
old-location: ifsk\file_disposition_information_ex.htm
old-project: ifsk
ms.assetid: CCFE4B09-F942-4D89-9013-159066D8E37A
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: FILE_DISPOSITION_INFORMATION_EX, FILE_DISPOSITION_INFORMATION_EX, *PFILE_DISPOSITION_INFORMATION_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_DISPOSITION_INFORMATION_EX
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# FILE_DISPOSITION_INFORMATION_EX structure



## -description
<p>The <b>FILE_DISPOSITION_INFORMATION_EX</b> structure is used as an argument to the <a href="kernel.zwsetinformationfileex">ZwSetInformationFileEx</a> routine and indicates how the operating system should delete a file.</p>


## -syntax

````
typedef struct _FILE_DISPOSITION_INFORMATION_EX {
   Flags;
} FILE_DISPOSITION_INFORMATION_EX, *PFILE_DISPOSITION_INFORMATION_EX;
````


## -struct-fields
<dl>

### -field <b>Flags</b>

<dd>
<p>Specifies what action(s) the system should take with a specific file while deleting.</p>
<table>
<tr>
<th>Flag Name</th>
<th>
                   Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>FILE_DISPOSITION_DO_NOT_DELETE</td>
<td>
                  0x00000000
                </td>
<td>Specifies the system should not delete a file.</td>
</tr>
<tr>
<td>FILE_DISPOSITION_DELETE</td>
<td>0x00000001</td>
<td>Specifies the system should delete a file.</td>
</tr>
<tr>
<td>FILE_DISPOSITION_POSIX_SEMANTICS</td>
<td>0x00000002</td>
<td>Specifies the system should perform a POSIX-style delete.</td>
</tr>
<tr>
<td>FILE_DISPOSITION_FORCE_IMAGE_SECTION_CHECK</td>
<td>0x00000004</td>
<td>Specifies the system should force an image section check. </td>
</tr>
<tr>
<td>FILE_DISPOSITION_ON_CLOSE </td>
<td>0x00000008</td>
<td>Specifies if the system sets or clears the on-close state.</td>
</tr>
</table>
<p> </p>
</dd>
</dl>

## -remarks
<p>The caller must have DELETE access to a given file to call ZwSetInformationFile with <b>FILE_DISPOSITION_DELETE</b>. </p>

<p>Normally a file marked for deletion is not actually deleted until all open handles for the file have been closed and the link count for the file is zero.  When marking a file for deletion using <b>FILE_DISPOSITION_POSIX_SEMANTICS</b>, the link gets removed from the visible namespace as soon as the POSIX delete handle has been closed, but the file’s data streams remain accessible by other existing handles until the last handle has been closed.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_DISPOSITION_INFORMATION_EX structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
