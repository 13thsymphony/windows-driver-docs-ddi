---
UID: NS:ntifs._FSCTL_OFFLOAD_READ_INPUT
title: "_FSCTL_OFFLOAD_READ_INPUT"
author: windows-driver-content
description: The FSCTL_OFFLOAD_READ_INPUT structure contains the input for the FSCTL_OFFLOAD_READ control code request.
old-location: ifsk\fsctl_offload_read_input.htm
old-project: ifsk
ms.assetid: 11F9FFC6-D2F6-4CCA-9459-CF2639AE652D
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FSCTL_OFFLOAD_READ_INPUT structure [Installable File System Drivers], FSCTL_OFFLOAD_READ_INPUT, *PFSCTL_OFFLOAD_READ_INPUT, PFSCTL_OFFLOAD_READ_INPUT structure pointer [Installable File System Drivers], _FSCTL_OFFLOAD_READ_INPUT, ntifs/PFSCTL_OFFLOAD_READ_INPUT, PFSCTL_OFFLOAD_READ_INPUT, ifsk.fsctl_offload_read_input, ntifs/FSCTL_OFFLOAD_READ_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	ntifs.h
apiname:
-	FSCTL_OFFLOAD_READ_INPUT
product: Windows
targetos: Windows
req.typenames: FSCTL_OFFLOAD_READ_INPUT, *PFSCTL_OFFLOAD_READ_INPUT
---

# _FSCTL_OFFLOAD_READ_INPUT structure
The <b>FSCTL_OFFLOAD_READ_INPUT</b> structure contains the input for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451101">FSCTL_OFFLOAD_READ</a> control code request.

## Syntax
````
typedef struct _FSCTL_OFFLOAD_READ_INPUT {
  ULONG     Size;
  ULONG     Flags;
  ULONG     TokenTimeToLive;
  ULONG     Reserved;
  ULONGLONG FileOffset;
  ULONGLONG Length;
} FSCTL_OFFLOAD_READ_INPUT, *PFSCTL_OFFLOAD_READ_INPUT;
````

## Members


`CopyLength`



`FileOffset`

The position in the file to start reading from. The offset value must be aligned to a logical sector boundary on the volume.

`Flags`

This member is not used. Set to 0.

`Reserved`

Reserved.

`Size`

The size of this structure. Set this member to <b>sizeof</b>(FSCTL_OFFLOAD_READ_INPUT).

`TokenTimeToLive`

The time, in milliseconds, for which the read operation remains valid. The default time-to-live is 0. The recommended value for time-to-live is also 0.

## Remarks
The  storage device's copy provider retains the data read for the duration in <b>TokenTimeToLive</b>. Multiple writes with the same token can be performed until the time in <b>TokenTimeToLive</b> expires.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451101">FSCTL_OFFLOAD_READ</a>



<a href="..\ntifs\ns-ntifs-_fsctl_offload_read_output.md">FSCTL_OFFLOAD_READ_OUTPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSCTL_OFFLOAD_READ_INPUT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>