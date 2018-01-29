---
UID : NF:wdm.MmGetMdlByteCount
title : MmGetMdlByteCount macro
author : windows-driver-content
description : The MmGetMdlByteCount macro returns the length, in bytes, of the buffer described by the specified MDL.
old-location : kernel\mmgetmdlbytecount.htm
old-project : Benchmark
ms.assetid : a0493418-2ce2-4917-bf9f-e4dc726a3847
ms.author : windowsdriverdev
ms.date : 1/12/2018
ms.keywords : MmGetMdlByteCount macro [Tools], wdm/MmGetMdlByteCount, kernel.mmgetmdlbytecount, k106_f750d750-c5ca-44cf-b8f1-f52d2eb8bc27.xml, MmGetMdlByteCount
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedReadA, MdlAfterReqCompletedWriteA
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wdm.h
req.dll : 
req.irql : Any level (see Remarks section)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# MmGetMdlByteCount function
The <b>MmGetMdlByteCount</b> macro returns the length, in bytes, of the buffer described by the specified MDL.

## Syntax

````
ULONG MmGetMdlByteCount(
  [in] PMDL Mdl
);
````

## Parameters

`Mdl`

A pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure that describes the layout of a virtual memory buffer in physical memory. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.


## Return Value

None

## Remarks

Callers of <b>MmGetMdlByteCount</b> can be running at any IRQL. Usually, callers are running at IRQL &lt;= DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | Any level (see Remarks section) |
| **DDI compliance rules** | MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedReadA, MdlAfterReqCompletedWriteA |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554533">MmGetMdlByteOffset</a>

<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>