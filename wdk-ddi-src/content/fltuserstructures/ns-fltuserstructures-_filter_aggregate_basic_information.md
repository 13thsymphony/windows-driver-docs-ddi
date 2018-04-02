---
UID: NS:fltuserstructures._FILTER_AGGREGATE_BASIC_INFORMATION
title: "_FILTER_AGGREGATE_BASIC_INFORMATION"
author: windows-driver-content
description: The FILTER_AGGREGATE_BASIC_INFORMATION structure contains basic information for a minifilter or legacy filter driver.
old-location: ifsk\filter_aggregate_basic_information.htm
old-project: ifsk
ms.assetid: c60ac4b8-3e55-42c8-a693-4fc6bbec0de8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFILTER_AGGREGATE_BASIC_INFORMATION, FILTER_AGGREGATE_BASIC_INFORMATION, FILTER_AGGREGATE_BASIC_INFORMATION structure [Installable File System Drivers], FltSystemStructures_b8f9faf4-0b81-4536-8f86-1e3f7938c3a4.xml, PFILTER_AGGREGATE_BASIC_INFORMATION, PFILTER_AGGREGATE_BASIC_INFORMATION structure pointer [Installable File System Drivers], _FILTER_AGGREGATE_BASIC_INFORMATION, fltuserstructures/FILTER_AGGREGATE_BASIC_INFORMATION, fltuserstructures/PFILTER_AGGREGATE_BASIC_INFORMATION, ifsk.filter_aggregate_basic_information"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltuserstructures.h
req.include-header: FltUser.h, FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Microsoft Windows Server 2003 SP1 and Windows XP SP2 with filter manager rollup.  For more information on the filter manager rollup package for Windows XP SP2, see article 914882, "The filter manager rollup package for Windows XP SP2," in the Microsoft Knowledge Base.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltuserstructures.h
api_name:
-	FILTER_AGGREGATE_BASIC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILTER_AGGREGATE_BASIC_INFORMATION, *PFILTER_AGGREGATE_BASIC_INFORMATION
---

# _FILTER_AGGREGATE_BASIC_INFORMATION structure
The FILTER_AGGREGATE_BASIC_INFORMATION structure contains basic information for a minifilter or legacy filter driver.

## Syntax
```
typedef struct _FILTER_AGGREGATE_BASIC_INFORMATION {
  ULONG NextEntryOffset;
  ULONG Flags;
  union {
    struct {
      ULONG  FrameID;
      ULONG  NumberOfInstances;
      USHORT FilterNameLength;
      USHORT FilterNameBufferOffset;
      USHORT FilterAltitudeLength;
      USHORT FilterAltitudeBufferOffset;
    } MiniFilter;
    struct {
      USHORT FilterNameLength;
      USHORT FilterNameBufferOffset;
    } LegacyFilter;
  } Type;
} *PFILTER_AGGREGATE_BASIC_INFORMATION, FILTER_AGGREGATE_BASIC_INFORMATION;
```

## Members


`NextEntryOffset`

Byte offset of the next FILTER_AGGREGATE_BASIC_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one.

`Flags`

Indicates whether the filter driver is a legacy filter or a minifilter.  This member must be one of the following values.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLTFL_AGGREGATE_INFO_IS_MINIFILTER

</td>
<td>
The filter is a minifilter - use the <b>MiniFilter</b> portion of the union.

</td>
</tr>
<tr>
<td>
FLTFL_AGGREGATE_INFO_IS_LEGACYFILTER

</td>
<td>
The filter is a legacy filter - use the <b>LegacyFilter</b> portion of the union.

</td>
</tr>
</table>

`Type`



## Remarks
The FILTER_AGGREGATE_BASIC_INFORMATION structure is passed as a parameter to routines such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff540485">FilterFindFirst</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff540488">FilterFindNext</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff540500">FilterGetInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff542060">FltEnumerateFilterInformation</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543053">FltGetFilterInformation</a>. 

This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This structure is available starting with Microsoft Windows Server 2003 SP1 and Windows XP SP2 with filter manager rollup.  For more information on the filter manager rollup package for Windows XP SP2, see article 914882, "The filter manager rollup package for Windows XP SP2," in the Microsoft Knowledge Base. This structure is available starting with Microsoft Windows Server 2003 SP1 and Windows XP SP2 with filter manager rollup.  For more information on the filter manager rollup package for Windows XP SP2, see article 914882, "The filter manager rollup package for Windows XP SP2," in the Microsoft Knowledge Base. |
| **Header** | fltuserstructures.h (include FltUser.h, FltKernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541567">FILTER_AGGREGATE_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541587">FILTER_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540481">FilterFindClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540485">FilterFindFirst</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540488">FilterFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540500">FilterGetInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542060">FltEnumerateFilterInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543053">FltGetFilterInformation</a>