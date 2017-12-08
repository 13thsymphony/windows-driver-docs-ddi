---
UID: NS.NTIFS._FILE_LINKS_INFORMATION
title: _FILE_LINKS_INFORMATION
author: windows-driver-content
description: The FILE_LINKS_INFORMATION structure is used to query NTFS hard links to an existing file.
old-location: ifsk\file_links_information.htm
old-project: ifsk
ms.assetid: adf1d2f3-4395-43d9-8157-e9f246e2bba8
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _FILE_LINKS_INFORMATION, *PFILE_LINKS_INFORMATION, FILE_LINKS_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_LINKS_INFORMATION
req.alt-loc: ntifs.h
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
---

# _FILE_LINKS_INFORMATION structure



## -description
The <b>FILE_LINKS_INFORMATION</b> structure is used to query NTFS hard links to an existing file.


## -syntax

````
typedef struct _FILE_LINKS_INFORMATION {
  ULONG                       BytesNeeded;
  ULONG                       EntriesReturned;
  FILE_LINK_ENTRY_INFORMATION Entry;
} FILE_LINKS_INFORMATION, *PFILE_LINKS_INFORMATION;
````


## -struct-fields

### -field BytesNeeded

The number of bytes needed to hold all available names returned using the <b>Entry</b> member. This value must be greater than 0.

### -field EntriesReturned

The number of <a href="ifsk.file_link_entry_information">FILE_LINK_ENTRY_INFORMATION</a> structures that have been returned using the <b>Entry</b> member. 

### -field Entry

A buffer that contains the returned <a href="ifsk.file_link_entry_information">FILE_LINK_ENTRY_INFORMATION</a> structures. 

## -remarks
If the member <b>EntriesReturned</b> has a value of 0, there is not enough available memory to return an entry. The error STATUS_BUFFER_OVERFLOW (0x80000005) indicates that not all available entries were returned.

The member <b>Entry</b> is the first <a href="ifsk.file_link_entry_information">FILE_LINK_ENTRY_INFORMATION</a> structure in a list of entries. Each entry is located <b>sizeof</b>(FILE_LINK_ENTRY_INFORMATION) + ((FileNameLength - 1 ) * <b>sizeof</b>(WCHAR)) from the previous entry when the FileNameLength member of <b>FILE_LINK_ENTRY_INFORMATION</b> &gt; 1. Otherwise, each entry is located <b>sizeof</b>(FILE_LINK_ENTRY_INFORMATION) from the previous entry.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows Vista.
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
</table>