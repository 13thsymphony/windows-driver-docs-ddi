---
UID: NF:wdm.ClfsLsnCreate
title: ClfsLsnCreate function
author: windows-driver-content
description: The ClfsLsnCreate routine creates a log sequence number (LSN), given a container identifier, a block offset, and a record sequence number.
old-location: kernel\clfslsncreate.htm
old-project: kernel
ms.assetid: 2b183911-0c4d-4b67-834d-e876d22c99af
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ClfsLsnCreate routine [Kernel-Mode Driver Architecture], wdm/ClfsLsnCreate, ClfsLsnCreate, kernel.clfslsncreate, Clfs_5eea5630-3db0-45bb-8e16-c9e69081f972.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
apiname:
-	ClfsLsnCreate
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ClfsLsnCreate function
The <b>ClfsLsnCreate</b> routine creates a log sequence number (LSN), given a container identifier, a block offset, and a record sequence number.

## Syntax

````
CLFS_LSN ClfsLsnCreate(
  _In_ CLFS_CONTAINER_ID cidContainer,
  _In_ ULONG             offBlock,
  _In_ ULONG             cRecord
);
````

## Parameters

`cidContainer`

An integer in the range 0x0 through 0xFFFFFFFF that supplies the container identifier.

`offBlock`

The block offset. This parameter must be a multiple of 512.

`cRecord`

An integer in the range 0 - 511 that supplies the record sequence number.


## Return Value

<b>ClfsLsnCreate</b> returns a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure that represents the container identifier, block offset, and record sequence number supplied by the caller.

## Remarks

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

systems.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows. Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows. |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h) |
| **Library** | Clfs.lib |
| **DLL** | Clfs.sys |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-clfslsnblockoffset.md">ClfsLsnBlockOffset</a>



<a href="..\wdm\nf-wdm-clfslsncontainer.md">ClfsLsnContainer</a>



<a href="..\wdm\nf-wdm-clfslsnrecordsequence.md">ClfsLsnRecordSequence</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsLsnCreate routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>