---
UID: NF:mrx.__RxFillAndInstallFastIoDispatch
title: "__RxFillAndInstallFastIoDispatch function"
author: windows-driver-content
description: RxFillAndInstallFastIoDispatch fills out a fast I/O dispatch vector to be identical with the normal dispatch I/O vector and installs it into the driver object associated with the device object passed.
old-location: ifsk\__rxfillandinstallfastiodispatch.htm
old-project: ifsk
ms.assetid: 4619a1aa-0c91-4b77-abbf-077f28437e0f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "__RxFillAndInstallFastIoDispatch, __RxFillAndInstallFastIoDispatch function [Installable File System Drivers], ifsk.__rxfillandinstallfastiodispatch, mrx/__RxFillAndInstallFastIoDispatch, rxref_5898351a-a474-44bb-8ba0-3d2edf81d073.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mrx.h
req.include-header: Mrx.h
req.target-type: Desktop
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mrx.h
api_name:
-	__RxFillAndInstallFastIoDispatch
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---


# __RxFillAndInstallFastIoDispatch function
<b>RxFillAndInstallFastIoDispatch</b> fills out a fast I/O dispatch vector to be identical with the normal dispatch I/O vector and installs it into the driver object associated with the device object passed.

## Syntax

````
VOID __RxFillAndInstallFastIoDispatch(
  _In_    PRDBSS_DEVICE_OBJECT RxDeviceObject,
  _Inout_ PFAST_IO_DISPATCH    FastIoDispatch,
  _In_    ULONG                FastIoDispatchSize
);
````

## Parameters

`RxDeviceObject`

A pointer to the RDBSS device object for this network redirector.

`FastIoDispatch`

A pointer to the fast I/O dispatch table to fill in and use.

`FastIoDispatchSize`

The size, in bytes, of the fast I/O dispatch table passed.


## Return Value

None

## Remarks

The <b>__RxFillAndInstallFastIoDispatch</b> routine is implemented differently for monolithic and non-monolithic drivers network mini-redirector. 

For non-monolithic network mini-redirector drivers, such as the Microsoft SMB redirector that links to rdbss.sys dynamically, <b>__RxFillAndInstallFastIoDispatch</b> is a convenience routine that copies the normal dispatch I/O vector table routines to the fast I/O dispatch vector table. This routine would normally be used by a non-monolithic network mini-redirector to fill out the fast I/O dispatch table before calling <a href="..\mrx\nf-mrx-rxregisterminirdr.md">RxRegisterMiniRdr</a>. This routine uses the minimum of the <i>FastIoDispatchSize</i> parameter and the size of the FAST_IO_DISPATCH structure defined in ntifs.h to determine the number of bytes to copy.

For monolithic network mini-redirectors built by developers, the <b>__RxFillAndInstallFastIoDispatch</b> routine does nothing.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mrx.h (include Mrx.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\mrx\nf-mrx-rxstartminirdr.md">RxStartMiniRdr</a>



<a href="..\mrx\nf-mrx-rxregisterminirdr.md">RxRegisterMinirdr</a>



<a href="..\mrx\nf-mrx-rxsetdomainformailslotbroadcast.md">RxSetDomainForMailslotBroadcast</a>



<a href="..\mrx\nf-mrx-rxstopminirdr.md">RxStopMiniRdr</a>