---
UID: NS:wdm._KBUGCHECK_DUMP_IO
title: "_KBUGCHECK_DUMP_IO"
author: windows-driver-content
description: The KBUGCHECK_DUMP_IO structure describes an I/O operation on the crash dump file.
old-location: kernel\kbugcheck_dump_io.htm
old-project: kernel
ms.assetid: d1c246bd-314d-475f-9df8-f1bf90355a5a
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PKBUGCHECK_DUMP_IO, KBUGCHECK_DUMP_IO, KBUGCHECK_DUMP_IO structure [Kernel-Mode Driver Architecture], PKBUGCHECK_DUMP_IO, PKBUGCHECK_DUMP_IO structure pointer [Kernel-Mode Driver Architecture], _KBUGCHECK_DUMP_IO, kernel.kbugcheck_dump_io, kstruct_c_a6201416-346e-4100-882c-329dd3ae1843.xml, wdm/KBUGCHECK_DUMP_IO, wdm/PKBUGCHECK_DUMP_IO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system.
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
-	KBUGCHECK_DUMP_IO
product:
- Windows
targetos: Windows
req.typenames: KBUGCHECK_DUMP_IO, *PKBUGCHECK_DUMP_IO
req.product: Windows 10 or later.
---

# _KBUGCHECK_DUMP_IO structure
The <b>KBUGCHECK_DUMP_IO</b> structure describes an I/O operation on the crash dump file.

## Syntax
```
typedef struct _KBUGCHECK_DUMP_IO {
  IN ULONG64                Offset;
  IN PVOID                  Buffer;
  IN ULONG                  BufferLength;
  IN KBUGCHECK_DUMP_IO_TYPE Type;
} *PKBUGCHECK_DUMP_IO, KBUGCHECK_DUMP_IO;
```

## Members


`Offset`

Specifies the current offset in the crash dump file, or -1 if the crash dump file is being written sequentially.

`Buffer`

Pointer to a buffer that contains the current data to be written to the dump file.

`BufferLength`

Specifies the length of the buffer, in bytes, that is specified by the <b>Buffer</b> member.

`Type`

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551871">KBUGCHECK_DUMP_IO_TYPE</a> value that signifies the type of data to be written to the dump file.

## Remarks
For information about how this structure is used, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Microsoft Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system. Available on Microsoft Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551871">KBUGCHECK_DUMP_IO_TYPE</a>