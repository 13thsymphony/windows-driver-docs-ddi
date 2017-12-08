---
UID: NS.ntifs._OPEN_REPARSE_LIST_ENTRY
title: OPEN_REPARSE_LIST_ENTRY
author: windows-driver-content
description: This structure supports callers opening specific reparse points without inhibiting reparse behavior for all classes of reparse points.
old-location: ifsk\open_reparse_list_entry_.htm
old-project: ifsk
ms.assetid: A6D28F60-FA38-45EA-9E3C-D2E6F899333E
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: OPEN_REPARSE_LIST_ENTRY, OPEN_REPARSE_LIST_ENTRY, *POPEN_REPARSE_LIST_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OPEN_REPARSE_LIST_ENTRY
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
req.iface: 
---

# OPEN_REPARSE_LIST_ENTRY structure



## -description
<p>This structure supports callers opening specific reparse points without
inhibiting reparse behavior for all classes of reparse points.</p>


## -syntax

````
typedef struct _OPEN_REPARSE_LIST_ENTRY  {
  LIST_ENTRY OpenReparseListEntry;
  ULONG      ReparseTag;
  ULONG      Flags;
  GUID       ReparseGuid;
  USHORT     Size;
  USHORT     RemainingLength;
} OPEN_REPARSE_LIST_ENTRY , *POPEN_REPARSE_LIST_ENTRY ;
````


## -struct-fields
<dl>

### -field OpenReparseListEntry

<dd>
<p>The entry in the open reparse list.</p>
</dd>

### -field ReparseTag

<dd>
<p>The reparse tag that should be opened directly without returning <b>STATUS_REPARSE</b>. </p>
</dd>

### -field Flags

<dd>
<p>Flags that control behavior when a reparse point is encountered on a directory that may be non-empty (one whose reparse tag is  recognized by <b>FsRtlIsNonEmptyDirectoryReparsePointAllowed</b>)
.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="OPEN_REPARSE_POINT_TAG_ENCOUNTERED"></a><a id="open_reparse_point_tag_encountered"></a><dl>

### -field OPEN_REPARSE_POINT_TAG_ENCOUNTERED


### -field 0x00000001

</dl>
</td>
<td width="60%">
<p>Indicates that the object that was opened matched the given criteria.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="OPEN_REPARSE_POINT_REPARSE_IF_CHILD_EXISTS"></a><a id="open_reparse_point_reparse_if_child_exists"></a><dl>

### -field OPEN_REPARSE_POINT_REPARSE_IF_CHILD_EXISTS


### -field 0x00000002

</dl>
</td>
<td width="60%">
<p>Reparse on the directory if the reparse point is on a directory that is not the final path
    component, and the next path component exists.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="OPEN_REPARSE_POINT_REPARSE_IF_CHILD_NOT_EXISTS"></a><a id="open_reparse_point_reparse_if_child_not_exists"></a><dl>

### -field OPEN_REPARSE_POINT_REPARSE_IF_CHILD_NOT_EXISTS


### -field 0x00000004

</dl>
</td>
<td width="60%">
<p>Reparse on the directory if the reparse point is on a directory that is not the final path
    component, and the next path component does not exist.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="OPEN_REPARSE_POINT_REPARSE_IF_DIRECTORY_FINAL_COMPONENT"></a><a id="open_reparse_point_reparse_if_directory_final_component"></a><dl>

### -field OPEN_REPARSE_POINT_REPARSE_IF_DIRECTORY_FINAL_COMPONENT


### -field 0x00000008

</dl>
</td>
<td width="60%">
<p>Reparse on the directory if the reparse point is on a directory that is the final path
component
and <b>FILE_OPEN_REPARSE_POINT</b> has not been specified.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="OPEN_REPARSE_POINT_VERSION_EX"></a><a id="open_reparse_point_version_ex"></a><dl>

### -field OPEN_REPARSE_POINT_VERSION_EX


### -field 0x80000000

</dl>
</td>
<td width="60%">
<p>Indicates that the fields of this structure are valid.</p>
</td>
</tr>
</table>
<p> </p>
<div class="alert"><b>Note</b>  When the <b>OPEN_REPARSE_POINT_REPARSE_IF_CHILD_EXISTS</b>,  <b>OPEN_REPARSE_POINT_REPARSE_IF_CHILD_NOT_EXISTS</b>, and <b>OPEN_REPARSE_POINT_REPARSE_IF_DIRECTORY_FINAL_COMPONENT</b> flags are used together at the same time, it indicates that the system is to reparse on any directory reparse point.</div>
<div> </div>
</dd>

### -field ReparseGuid

<dd>
<p>The GUID of the reparse tag that should be opened directly without returning <b>STATUS_REPARSE</b>.</p>
</dd>

### -field Size

<dd>
<p>The size of this structure.</p>
</dd>

### -field RemainingLength

<dd>
<p>The unprocessed path length when the reparse point was
    encountered.</p>
</dd>
</dl>

## -remarks
<p>This structure lets callers open specific reparse points without
  inhibiting reparse behavior for all classes of reparse points.
<a href="..\ntifs\ns-ntifs--open-reparse-list.md">OPEN_REPARSE_LIST</a> is a structure used in an ECP with <b>ECP_TYPE_OPEN_REPARSE_GUID</b> (<code>323eb6a8-affd-4d95-8230-863bce09d37a</code>). The <b>OPEN_REPARSE_LIST</b> points to a list of <b>OPEN_REPARSE_LIST_ENTRY</b>
structures specifying the tag and possibly GUID that should be
  opened directly without returning <b>STATUS_REPARSE</b>.
If a match is found, the corresponding <b>OPEN_REPARSE_LIST_ENTRY</b>  structure will have the <b>OPEN_REPARSE_POINT_TAG_ENCOUNTERED</b> flag set to indicate that the object that was opened matched the given criteria. If a match is found for a directory that is not the final path  component and <b>STATUS_REPARSE</b> is returned, the unprocessed path
  length will be set in the <b>RemainingLength</b> field.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10, version 1607</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h</dt>
</dl>
</td>
</tr>
</table>