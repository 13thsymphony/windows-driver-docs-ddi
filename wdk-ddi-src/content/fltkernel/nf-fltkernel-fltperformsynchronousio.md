---
UID: NF:fltkernel.FltPerformSynchronousIo
title: FltPerformSynchronousIo function
author: windows-driver-content
description: A minifilter driver calls FltPerformSynchronousIo to initiate a synchronous I/O operation after calling FltAllocateCallbackData to allocate a callback data structure for the operation.
old-location: ifsk\fltperformsynchronousio.htm
old-project: ifsk
ms.assetid: 14f5260a-b18d-4329-a81e-d24026d9a71d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_p_to_z_02aeeeab-6a33-4336-aaa4-810bd70850bc.xml, FltPerformSynchronousIo, FltPerformSynchronousIo routine [Installable File System Drivers], fltkernel/FltPerformSynchronousIo, ifsk.fltperformsynchronousio
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltPerformSynchronousIo
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltPerformSynchronousIo function
A minifilter driver calls <b>FltPerformSynchronousIo</b> to initiate a synchronous I/O operation after calling <a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a> to allocate a callback data structure for the operation.

## Syntax

````
VOID FltPerformSynchronousIo(
  _Inout_ PFLT_CALLBACK_DATA CallbackData
);
````

## Parameters

`CallbackData`

Pointer to a callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure allocated by a previous call to <a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a>. This parameter is required and cannot be <b>NULL</b>. The caller is responsible for freeing this structure when it is no longer needed by calling <a href="..\fltkernel\nf-fltkernel-fltfreecallbackdata.md">FltFreeCallbackData</a>.


## Return Value

None

## Remarks

A minifilter driver calls <b>FltPerformSynchronousIo</b> to initiate a synchronous I/O operation. 

Minifilter drivers can only initiate IRP-based I/O operations. They cannot initiate fast I/O or file system filter (FSFilter) callback operations. 

<b>FltPerformSynchronousIo</b> sends the I/O operation only to the minifilter driver instances attached below the initiating instance (specified in the <i>Instance</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a>), and the file system. Minifilter drivers attached above the specified instance do not receive the I/O operation. 

Minifilter drivers should use <b>FltPerformSynchronousIo</b> only in cases where routines such as the following cannot be used: 


<a href="..\fltkernel\nf-fltkernel-fltclose.md">FltClose</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefile.md">FltCreateFile</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryinformationfile.md">FltQueryInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>



<a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a>



<a href="..\fltkernel\nf-fltkernel-flttagfile.md">FltTagFile</a>



<a href="..\fltkernel\nf-fltkernel-fltuntagfile.md">FltUntagFile</a>



<a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>


After <b>FltPerformSynchronousIo</b> returns, the caller can reissue the I/O operation by calling <a href="..\fltkernel\nf-fltkernel-fltreissuesynchronousio.md">FltReissueSynchronousIo</a>. Alternatively, the caller can free the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure by calling <a href="..\fltkernel\nf-fltkernel-fltfreecallbackdata.md">FltFreeCallbackData</a> or prepare it to be reused by calling <a href="..\fltkernel\nf-fltkernel-fltreusecallbackdata.md">FltReuseCallbackData</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltuntagfile.md">FltUntagFile</a>



<a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>



<a href="..\fltkernel\nf-fltkernel-fltclose.md">FltClose</a>



<a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltreusecallbackdata.md">FltReuseCallbackData</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-flttagfile.md">FltTagFile</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryinformationfile.md">FltQueryInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltreissuesynchronousio.md">FltReissueSynchronousIo</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefile.md">FltCreateFile</a>



<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>



<a href="..\fltkernel\nf-fltkernel-fltfreecallbackdata.md">FltFreeCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>