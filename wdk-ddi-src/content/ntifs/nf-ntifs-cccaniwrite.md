---
UID : NF:ntifs.CcCanIWrite
title : CcCanIWrite function
author : windows-driver-content
description : The CcCanIWrite routine determines whether the caller can write to a cached file.
old-location : ifsk\cccaniwrite.htm
old-project : ifsk
ms.assetid : 04b1521f-906f-493d-9ca6-6d97c6a80bdb
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : CcCanIWrite
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : CcCanIWrite
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : 
req.typenames : TOKEN_TYPE
---


# CcCanIWrite function
The <b>CcCanIWrite</b> routine determines whether the caller can write to a cached file.

## Syntax

````
BOOLEAN CcCanIWrite(
  _In_ PFILE_OBJECT FileObject,
  _In_ ULONG        BytesToWrite,
  _In_ BOOLEAN      Wait,
  _In_ UCHAR        Retrying
);
````

## Parameters

`FileObject`

Pointer to a file object for the cached file.

`BytesToWrite`

Number of bytes to be written.

`Wait`

Set to <b>TRUE</b> if the caller can be put into a wait state until it can write to the cached file, <b>FALSE</b> otherwise.

`Retrying`

Set to <b>FALSE</b> if this is the first time <b>CcCanIWrite</b> is being called for this write request, <b>TRUE</b> otherwise.


## Return Value

<b>CcCanIWrite</b> returns <b>TRUE</b> if the cache manager can accept the write request, <b>FALSE</b> otherwise.

## Remarks

<b>CcCanIWrite</b> should be called before calling <a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a> or <a href="..\ntifs\nf-ntifs-ccfastcopywrite.md">CcFastCopyWrite</a>.

If <b>CcCanIWrite</b> returns <b>TRUE</b>, the caller can immediately call <a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a> or <a href="..\ntifs\nf-ntifs-ccfastcopywrite.md">CcFastCopyWrite</a>.

If <b>CcCanIWrite</b> returns <b>FALSE</b>, the caller must instead call <a href="..\ntifs\nf-ntifs-ccdeferwrite.md">CcDeferWrite</a> to defer the write request.

Generally speaking, the cache manager can accept a write request if the following conditions are true:

The amount of data to be written is not too large.

There is enough memory to perform the write operation.

The number of dirty pages in the system cache does not exceed the dirty page threshold (CcDirtyPageThreshold).

If a per-file dirty page threshold exists for this file, it is not exceeded by the number of dirty pages for this file in the system cache.

To cache a file, use <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccdeferwrite.md">CcDeferWrite</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccfastcopywrite.md">CcFastCopyWrite</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccsetdirtypagethreshold.md">CcSetDirtyPageThreshold</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcCanIWrite routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>