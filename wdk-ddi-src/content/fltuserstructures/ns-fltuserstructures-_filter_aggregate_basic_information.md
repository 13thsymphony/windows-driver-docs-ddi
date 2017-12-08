---
UID: NS.FLTUSERSTRUCTURES._FILTER_AGGREGATE_BASIC_INFORMATION
title: _FILTER_AGGREGATE_BASIC_INFORMATION
author: windows-driver-content
description: The FILTER_AGGREGATE_BASIC_INFORMATION structure contains basic information for a minifilter or legacy filter driver.
old-location: ifsk\filter_aggregate_basic_information.htm
old-project: ifsk
ms.assetid: c60ac4b8-3e55-42c8-a693-4fc6bbec0de8
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _FILTER_AGGREGATE_BASIC_INFORMATION, *PFILTER_AGGREGATE_BASIC_INFORMATION, FILTER_AGGREGATE_BASIC_INFORMATION
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
req.alt-api: FILTER_AGGREGATE_BASIC_INFORMATION
req.alt-loc: fltuserstructures.h
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
---

# _FILTER_AGGREGATE_BASIC_INFORMATION structure



## -description
The FILTER_AGGREGATE_BASIC_INFORMATION structure contains basic information for a minifilter or legacy filter driver. 


## -syntax

````
typedef struct _FILTER_AGGREGATE_BASIC_INFORMATION {
  ULONG NextEntryOffset;
  ULONG Flags;
  union {
    struct {
      ULONG  FrameID;
      ULONG  NumberOfInstances;
      USHORT FilterNameLength;
      USHORT FilterNameBufferOffset;
      USHORT FilterAltitudeLength;
      USHORT FilterAltitudeBufferOffset;
    } MiniFilter;
    struct {
      USHORT FilterNameLength;
      USHORT FilterNameBufferOffset;
    } LegacyFilter;
  } Type;
} FILTER_AGGREGATE_BASIC_INFORMATION, *PFILTER_AGGREGATE_BASIC_INFORMATION;
````


## -struct-fields

### -field NextEntryOffset

Byte offset of the next FILTER_AGGREGATE_BASIC_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one. 

### -field Flags

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
 

### -field Type

 

### -field MiniFilter

 

### -field FrameID

Zero-based index of the current frame. 

### -field NumberOfInstances

Number of instances that currently exist for the minifilter. 

### -field FilterNameLength

Length, in bytes, of the filter name. 

### -field FilterNameBufferOffset

Byte offset of the first character of the filter name string. 

### -field FilterAltitudeLength

Length, in bytes, of the minifilter altitude string. 

### -field FilterAltitudeBufferOffset

Byte offset of the first character of the minifilter altitude string. 
</dd>
</dl>

### -field LegacyFilter

 

### -field FilterNameLength

Length, in bytes, of the filter name. 

### -field FilterNameBufferOffset

Byte offset of the first character of the filter name string. 
</dd>
</dl>
</dd>
</dl>

## -remarks
The FILTER_AGGREGATE_BASIC_INFORMATION structure is passed as a parameter to routines such as <a href="ifsk.filterfindfirst">FilterFindFirst</a>, <a href="ifsk.filterfindnext">FilterFindNext</a>, <a href="ifsk.filtergetinformation">FilterGetInformation</a>, <a href="ifsk.fltenumeratefilterinformation">FltEnumerateFilterInformation</a>, and <a href="ifsk.fltgetfilterinformation">FltGetFilterInformation</a>. 

This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
This structure is available starting with Microsoft Windows Server 2003 SP1 and Windows XP SP2 with filter manager rollup.  For more information on the filter manager rollup package for Windows XP SP2, see article 914882, "The filter manager rollup package for Windows XP SP2," in the Microsoft Knowledge Base. 
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Fltuserstructures.h (include FltUser.h or FltKernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.filter_aggregate_standard_information">FILTER_AGGREGATE_STANDARD_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.filter_full_information">FILTER_FULL_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.filterfindclose">FilterFindClose</a>
</dt>
<dt>
<a href="ifsk.filterfindfirst">FilterFindFirst</a>
</dt>
<dt>
<a href="ifsk.filterfindnext">FilterFindNext</a>
</dt>
<dt>
<a href="ifsk.filtergetinformation">FilterGetInformation</a>
</dt>
<dt>
<a href="ifsk.fltenumeratefilterinformation">FltEnumerateFilterInformation</a>
</dt>
<dt>
<a href="ifsk.fltgetfilterinformation">FltGetFilterInformation</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILTER_AGGREGATE_BASIC_INFORMATION structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
