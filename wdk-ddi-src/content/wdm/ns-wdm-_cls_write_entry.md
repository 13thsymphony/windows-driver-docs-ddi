---
UID: NS:wdm._CLS_WRITE_ENTRY
title: "_CLS_WRITE_ENTRY"
author: windows-driver-content
description: The CLFS_WRITE_ENTRY structure holds the address and size of a buffer that contains one unit of data to be written to a Common Log File System (CLFS) stream.
old-location: kernel\clfs_write_entry.htm
old-project: kernel
ms.assetid: 4b008fc7-35fe-40f9-8475-1a2ac04edb58
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PCLS_WRITE_ENTRY, PPCLFS_WRITE_ENTRY, CLS_WRITE_ENTRY, wdm/CLFS_WRITE_ENTRY, PPCLS_WRITE_ENTRY structure pointer [Kernel-Mode Driver Architecture], PPCLS_WRITE_ENTRY, kernel.clfs_write_entry, CLS_WRITE_ENTRY structure [Kernel-Mode Driver Architecture], _CLS_WRITE_ENTRY, wdm/PPCLS_WRITE_ENTRY, kstruct_a_331b7685-f256-4071-8edf-e517afc2b8cc.xml, *PCLFS_WRITE_ENTRY, PCLS_WRITE_ENTRY structure pointer [Kernel-Mode Driver Architecture], wdm/PCLS_WRITE_ENTRY, PCLFS_WRITE_ENTRY, *PCLS_WRITE_ENTRY, PPCLFS_WRITE_ENTRY structure pointer [Kernel-Mode Driver Architecture], wdm/CLS_WRITE_ENTRY, CLFS_WRITE_ENTRY structure [Kernel-Mode Driver Architecture], wdm/PPCLFS_WRITE_ENTRY, CLFS_WRITE_ENTRY, PCLFS_WRITE_ENTRY structure pointer [Kernel-Mode Driver Architecture], wdm/PCLFS_WRITE_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	CLS_WRITE_ENTRY
product: Windows
targetos: Windows
req.typenames: CLS_WRITE_ENTRY, PPCLS_WRITE_ENTRY, *PCLS_WRITE_ENTRY
req.product: Windows 10 or later.
---

# _CLS_WRITE_ENTRY structure
The <b>CLFS_WRITE_ENTRY</b> structure holds the address and size of a buffer that contains one unit of data to be written to a Common Log File System (CLFS) stream.

## Syntax
````
typedef struct _CLS_WRITE_ENTRY {
  PVOID Buffer;
  ULONG ByteLength;
} CLS_WRITE_ENTRY, *PCLS_WRITE_ENTRY, **PPCLS_WRITE_ENTRY, CLFS_WRITE_ENTRY, *PCLFS_WRITE_ENTRY, **PPCLFS_WRITE_ENTRY;
````

## Members


`Buffer`

A pointer to the buffer that holds the data.

`ByteLength`

The size, in bytes, of the buffer pointed to by <b>Buffer</b>.

## Remarks
CLFS collects the buffers pointed to by several <b>CLFS_WRITE_ENTRY</b> structures into a single log record. The log record is then placed in a log I/O block along with other log records. Eventually the log I/O block is flushed to disk.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h) |

## See Also

<a href="..\wdm\nf-wdm-clfsreserveandappendlogaligned.md">ClfsReserveAndAppendLogAligned</a>



<a href="..\wdm\nf-wdm-clfsreserveandappendlog.md">ClfsReserveAndAppendLog</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLS_WRITE_ENTRY structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>