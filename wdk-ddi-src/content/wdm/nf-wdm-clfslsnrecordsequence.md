---
UID : NF:wdm.ClfsLsnRecordSequence
title : ClfsLsnRecordSequence function
author : windows-driver-content
description : The ClfsLsnRecordSequence routine returns the record sequence number contained in a specified LSN.
old-location : kernel\clfslsnrecordsequence.htm
old-project : kernel
ms.assetid : 407675de-4a06-49f7-9b43-c48b4c84ac7e
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.clfslsnrecordsequence, wdm/ClfsLsnRecordSequence, ClfsLsnRecordSequence, ClfsLsnRecordSequence routine [Kernel-Mode Driver Architecture], Clfs_a78f7923-d295-408c-9a52-16e5cc38ca31.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Clfs.lib
req.dll : Clfs.sys
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# ClfsLsnRecordSequence function
The <b>ClfsLsnRecordSequence</b> routine returns the record sequence number contained in a specified LSN.

## Syntax

````
ULONG ClfsLsnRecordSequence(
  _In_ const CLFS_LSN *plsn
);
````

## Parameters

`plsn`

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure from which the record sequence number is retrieved.


## Return Value

<b>ClfsLsnRecordSequence</b> returns the record sequence number contained in the LSN that is supplied by the caller.

## Remarks

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-clfslsnblockoffset.md">ClfsLsnBlockOffset</a>

<a href="..\wdm\nf-wdm-clfslsncontainer.md">ClfsLsnContainer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsLsnRecordSequence routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>