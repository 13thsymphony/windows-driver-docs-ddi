---
UID: NS:wdm._KBUGCHECK_SECONDARY_DUMP_DATA
title: "_KBUGCHECK_SECONDARY_DUMP_DATA"
author: windows-driver-content
description: The KBUGCHECK_SECONDARY_DUMP_DATA structure describes a section of driver-supplied data to be written by BugCheckSecondaryDumpDataCallback to the crash dump file.
old-location: kernel\kbugcheck_secondary_dump_data.htm
old-project: kernel
ms.assetid: dacb98cd-46bc-49d0-8ebd-29bb2dd5b713
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PKBUGCHECK_SECONDARY_DUMP_DATA, KBUGCHECK_SECONDARY_DUMP_DATA, KBUGCHECK_SECONDARY_DUMP_DATA structure [Kernel-Mode Driver Architecture], PKBUGCHECK_SECONDARY_DUMP_DATA, PKBUGCHECK_SECONDARY_DUMP_DATA structure pointer [Kernel-Mode Driver Architecture], _KBUGCHECK_SECONDARY_DUMP_DATA, kernel.kbugcheck_secondary_dump_data, kstruct_c_a9e0d726-41eb-4cf2-b2d4-c977be8750bb.xml, wdm/KBUGCHECK_SECONDARY_DUMP_DATA, wdm/PKBUGCHECK_SECONDARY_DUMP_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	KBUGCHECK_SECONDARY_DUMP_DATA
product: Windows
targetos: Windows
req.typenames: KBUGCHECK_SECONDARY_DUMP_DATA, *PKBUGCHECK_SECONDARY_DUMP_DATA
req.product: Windows 10 or later.
---

# _KBUGCHECK_SECONDARY_DUMP_DATA structure
The <b>KBUGCHECK_SECONDARY_DUMP_DATA</b> structure describes a section of driver-supplied data to be written by <a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a> to the crash dump file.

## Syntax
```
typedef struct _KBUGCHECK_SECONDARY_DUMP_DATA {
  IN PVOID  InBuffer;
  IN ULONG  InBufferLength;
  IN ULONG  MaximumAllowed;
  OUT GUID  Guid;
  OUT PVOID OutBuffer;
  OUT ULONG OutBufferLength;
} *PKBUGCHECK_SECONDARY_DUMP_DATA, KBUGCHECK_SECONDARY_DUMP_DATA;
```

## Members


`InBuffer`

Pointer to a buffer that is allocated by the system.

`InBufferLength`

Specifies the size of the buffer, in bytes, specified by the <b>InBuffer</b> member.

`MaximumAllowed`

Specifies the maximum amount of data that the <i>BugCheckSecondaryDumpDataCallback</i> routine can write to the crash dump file.

`Guid`

Specifies a GUID that identifies the driver's crash dump data. (Drivers must use unique GUIDs to mark their crash dump data. Use the GuidGen.exe tool to generate GUIDs for your driver. This tool is included in the Microsoft Windows SDK.)

`OutBuffer`

Pointer to the buffer where the driver writes its crash dump data, or <b>NULL</b>.

`OutBufferLength`

Specifies the size of the buffer, in bytes, that was specified by the <b>OutBuffer</b> member.

## Remarks
For more information about how this structure is used, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Microsoft Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system. Available on Microsoft Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>