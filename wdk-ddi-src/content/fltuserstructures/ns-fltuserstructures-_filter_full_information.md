---
UID: NS:fltuserstructures._FILTER_FULL_INFORMATION
title: "_FILTER_FULL_INFORMATION"
author: windows-driver-content
description: The FILTER_FULL_INFORMATION structure contains full information for a minifilter driver.
old-location: ifsk\filter_full_information.htm
old-project: ifsk
ms.assetid: fb592350-76e2-4655-b6db-854fd48aa827
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: fltuserstructures/FILTER_FULL_INFORMATION, fltuserstructures/PFILTER_FULL_INFORMATION, PFILTER_FULL_INFORMATION structure pointer [Installable File System Drivers], FltSystemStructures_e72c2545-4938-4a3e-b3c8-95fd7f46239a.xml, PFILTER_FULL_INFORMATION, FILTER_FULL_INFORMATION, _FILTER_FULL_INFORMATION, ifsk.filter_full_information, FILTER_FULL_INFORMATION structure [Installable File System Drivers], *PFILTER_FULL_INFORMATION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fltuserstructures.h
apiname:
-	FILTER_FULL_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PFILTER_FULL_INFORMATION, FILTER_FULL_INFORMATION"
---

# _FILTER_FULL_INFORMATION structure
The FILTER_FULL_INFORMATION structure contains full information for a minifilter driver.

## Syntax
````
typedef struct _FILTER_FULL_INFORMATION {
  ULONG  NextEntryOffset;
  ULONG  FrameID;
  ULONG  NumberOfInstances;
  USHORT FilterNameLength;
  WCHAR  FilterNameBuffer[1];
} FILTER_FULL_INFORMATION, *PFILTER_FULL_INFORMATION;
````

## Members


`FilterNameBuffer`

Specifies the first character of the filter name string. This character is followed in memory by the remainder of the string. The length of the string is specified by the <b>FilterNameLength</b> member. The string is Unicode and is not NULL-terminated.

`FilterNameLength`

Length, in bytes, of the minifilter name.

`FrameID`

Zero-based index of the current frame.

`NextEntryOffset`

Byte offset of the next FILTER_FULL_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one.

`NumberOfInstances`

Number of instances that currently exist for this minifilter.

## Remarks
The FILTER_FULL_INFORMATION structure is passed as a parameter to routines such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff540485">FilterFindFirst</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff540488">FilterFindNext</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff540500">FilterGetInformation</a>, <a href="..\fltkernel\nf-fltkernel-fltenumeratefilterinformation.md">FltEnumerateFilterInformation</a>, and <a href="..\fltkernel\nf-fltkernel-fltgetfilterinformation.md">FltGetFilterInformation</a>. 

This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | fltuserstructures.h (include FltUser.h, FltKernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540488">FilterFindNext</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_filter_aggregate_basic_information.md">FILTER_AGGREGATE_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540500">FilterGetInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltenumeratefilterinformation.md">FltEnumerateFilterInformation</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_filter_aggregate_standard_information.md">FILTER_AGGREGATE_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540481">FilterFindClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540485">FilterFindFirst</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilterinformation.md">FltGetFilterInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILTER_FULL_INFORMATION structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>