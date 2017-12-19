---
UID: NS.FLTUSERSTRUCTURES._FILTER_VOLUME_BASIC_INFORMATION
title: _FILTER_VOLUME_BASIC_INFORMATION
author: windows-driver-content
description: The caller-allocated FILTER_VOLUME_BASIC_INFORMATION structure contains basic information for a volume.
old-location: ifsk\filter_volume_basic_information.htm
old-project: ifsk
ms.assetid: f6b5ccc2-81d6-47be-94dd-cf92842de51c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _FILTER_VOLUME_BASIC_INFORMATION, PFILTER_VOLUME_BASIC_INFORMATION, *PFILTER_VOLUME_BASIC_INFORMATION, FILTER_VOLUME_BASIC_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltuserstructures.h
req.include-header: FltUser.h, FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILTER_VOLUME_BASIC_INFORMATION
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

# _FILTER_VOLUME_BASIC_INFORMATION structure



## -description
The caller-allocated FILTER_VOLUME_BASIC_INFORMATION  structure contains basic information for a volume.



## -syntax

````
typedef struct _FILTER_VOLUME_BASIC_INFORMATION {
  USHORT FilterVolumeNameLength;
  WCHAR  FilterVolumeName[1];
} FILTER_VOLUME_BASIC_INFORMATION, *PFILTER_VOLUME_BASIC_INFORMATION;
````


## -struct-fields

### -field FilterVolumeNameLength

Read-only length, in bytes, of the volume name.


### -field FilterVolumeName

Read-only name of the volume of <b>FilterVolumeNameLength</b> length.  This Unicode string is not NULL-terminated. 


## -remarks
Filter manager enumeration routines, such as <a href="ifsk.fltenumeratevolumeinformation">FltEnumerateVolumeInformation</a>, can fill a buffer with structures of type FILTER_VOLUME_BASIC_INFORMATION where each structure represents a volume known to filter manager.  This list of structures can contain multiple volumes with the same name.  For more information, see <a href="ifsk.understanding_volume_enumerations_with_duplicate_volume_names">Understanding Volume Enumerations with Duplicate Volume Names</a>.

The FILTER_VOLUME_BASIC_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each structure falls on an 8-byte boundary.

A FILTER_VOLUME_BASIC_INFORMATION structure can be allocated from paged or nonpaged pool.


## -requirements
<table>
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
<a href="ifsk.filter_volume_standard_information">FILTER_VOLUME_STANDARD_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.filtervolumefindclose">FilterVolumeFindClose</a>
</dt>
<dt>
<a href="ifsk.filtervolumefindfirst">FilterVolumeFindFirst</a>
</dt>
<dt>
<a href="ifsk.filtervolumefindnext">FilterVolumeFindNext</a>
</dt>
<dt>
<a href="ifsk.fltenumeratevolumeinformation">FltEnumerateVolumeInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILTER_VOLUME_BASIC_INFORMATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

