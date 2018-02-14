---
UID: NS:ntifs._QUERY_FILE_LAYOUT_OUTPUT
title: "_QUERY_FILE_LAYOUT_OUTPUT"
author: windows-driver-content
description: The QUERY_FILE_LAYOUT_OUTPUT structure serves as a header for the file layout entries that are returned from a FSCTL_QUERY_FILE_LAYOUT request.
old-location: ifsk\query_file_layout_output.htm
old-project: ifsk
ms.assetid: 204893BE-8B89-4BE4-BEDB-BF28DBAAACE9
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ntifs/QUERY_FILE_LAYOUT_OUTPUT, *PQUERY_FILE_LAYOUT_OUTPUT, ifsk.query_file_layout_output, PQUERY_FILE_LAYOUT_OUTPUT, ntifs/PQUERY_FILE_LAYOUT_OUTPUT, QUERY_FILE_LAYOUT_SINGLE_INSTANCED, _QUERY_FILE_LAYOUT_OUTPUT, PQUERY_FILE_LAYOUT_OUTPUT structure pointer [Installable File System Drivers], QUERY_FILE_LAYOUT_OUTPUT structure [Installable File System Drivers], QUERY_FILE_LAYOUT_OUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting in Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntifs.h
apiname:
-	QUERY_FILE_LAYOUT_OUTPUT
product: Windows
targetos: Windows
req.typenames: QUERY_FILE_LAYOUT_OUTPUT, *PQUERY_FILE_LAYOUT_OUTPUT
---

# _QUERY_FILE_LAYOUT_OUTPUT structure
The <b>QUERY_FILE_LAYOUT_OUTPUT</b> structure serves as a header for the file layout entries that are returned from a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451133">FSCTL_QUERY_FILE_LAYOUT</a> request.

## Syntax
````
typedef struct _QUERY_FILE_LAYOUT_OUTPUT {
  ULONG FileEntryCount;
  ULONG FirstFileOffset;
  ULONG Flags;
  ULONG Reserved;
} QUERY_FILE_LAYOUT_OUTPUT, *PQUERY_FILE_LAYOUT_OUTPUT;
````

## Members


`FileEntryCount`

The number of file entries that follow this structure.

`FirstFileOffset`

The offset in the user buffer for the first file entry.

`Flags`

Indicates the format of layout entries returned. Can be 0 or the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="QUERY_FILE_LAYOUT_SINGLE_INSTANCED"></a><a id="query_file_layout_single_instanced"></a><dl>
<dt><b>QUERY_FILE_LAYOUT_SINGLE_INSTANCED</b></dt>
</dl>
</td>
<td width="60%">
Single instances of stream and file layout entries are returned. When set, only one <b>STREAM_LAYOUT_ENTRY</b> structure is returned per stream and only one <b>FILE_LAYOUT_ENTRY</b> structure is returned per file. This flag is always set for NTFS.

</td>
</tr>
</table>

`Reserved`

Reserved.

## Remarks
The file layout entries that follow the <b>QUERY_FILE_LAYOUT_OUTPUT</b> structure are determined by the flags set in the <b>Flags</b> member of <a href="..\ntifs\ns-ntifs-_query_file_layout_input.md">QUERY_FILE_LAYOUT_INPUT</a> provided as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451133">FSCTL_QUERY_FILE_LAYOUT</a> request. A number of <b>FILE_LAYOUT_ENTRY</b> structures follow <b>QUERY_FILE_LAYOUT_OUTPUT</b>. Depending on the entries selected to return from a query, offsets in <b>FILE_LAYOUT_ENTRY</b> indicate where the additional informational entries are located in the user buffer. 

The following entry structures are returned when their corresponding inclusion flag is set in the <b>Flags</b> member of <a href="..\ntifs\ns-ntifs-_query_file_layout_input.md">QUERY_FILE_LAYOUT_INPUT</a>.<table>
<tr>
<th>Entry</th>
<th>Inclusion flag</th>
</tr>
<tr>
<td><b>FILE_LAYOUT_NAME_ENTRY</b></td>
<td><b>QUERY_FILE_LAYOUT_INCLUDE_NAMES</b></td>
</tr>
<tr>
<td><b>FILE_LAYOUT_INFO_ENTRY</b></td>
<td><b>QUERY_FILE_LAYOUT_INCLUDE_EXTRA_INFO</b></td>
</tr>
<tr>
<td><b>STREAM_LAYOUT_ENTRY</b></td>
<td><b>QUERY_FILE_LAYOUT_INCLUDE_STREAMS</b></td>
</tr>
<tr>
<td><b>STREAM_EXTENT_ENTRY</b></td>
<td><b>QUERY_FILE_LAYOUT_INCLUDE_EXTENTS</b></td>
</tr>
</table>
 



When multiple entries of the same type exist for a single <b>FILE_LAYOUT_ENTRY</b> structure, each informational entry structure has an offset member that indicates the location of the next entry. The chain of entry structures continues until the value of the offset member is 0.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting in Windows 8. Available starting in Windows 8. |
| **Header** | ntifs.h (include Ntifs.h) |

## See Also

<a href="..\ntifs\ns-ntifs-_query_file_layout_input.md">QUERY_FILE_LAYOUT_INPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451133">FSCTL_QUERY_FILE_LAYOUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20QUERY_FILE_LAYOUT_OUTPUT structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>