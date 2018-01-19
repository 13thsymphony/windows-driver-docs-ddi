---
UID : NF:ntifs.CcDeferWrite
title : CcDeferWrite function
author : windows-driver-content
description : The CcDeferWrite routine defers writing to a cached file.
old-location : ifsk\ccdeferwrite.htm
old-project : ifsk
ms.assetid : a655bcde-c627-4c90-8579-348ab0174c27
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : CcDeferWrite
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
req.alt-api : CcDeferWrite
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


# CcDeferWrite function
The <b>CcDeferWrite</b> routine defers writing to a cached file. The post routine that is supplied, is called by the cache manager when it can accommodate the write operation.

## Syntax

````
VOID CcDeferWrite(
  _In_ PFILE_OBJECT            FileObject,
  _In_ PCC_POST_DEFERRED_WRITE PostRoutine,
  _In_ PVOID                   Context1,
  _In_ PVOID                   Context2,
  _In_ ULONG                   BytesToWrite,
  _In_ BOOLEAN                 Retrying
);
````

## Parameters

`FileObject`

Pointer to a file object for the cached file to which the data is to be written.

`PostRoutine`

Address of a routine for the cache manager to call to write to the cached file. Note that it is possible that this routine will be called immediately, even if <a href="..\ntifs\nf-ntifs-cccaniwrite.md">CcCanIWrite</a> has just returned <b>FALSE</b> .

The post routine is defined in ntifs.h as:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID (*PCC_POST_DEFERRED_WRITE) (
    _In_ PVOID Context1,
    _In_ PVOID Context2
    );</pre>
</td>
</tr>
</table></span></div>

`Context1`

First parameter for the post routine at <i>PostRoutine</i>.

`Context2`

Second parameter for the post routine at <i>PostRoutine</i>.

`BytesToWrite`

Number of bytes of data to be written.

`Retrying`

Set to <b>FALSE</b> if the request is being posted for the first time, <b>TRUE</b> otherwise.


## Return Value

None

## Remarks

A file system would normally call <b>CcDeferWrite</b> after receiving a return value of <b>FALSE</b> from <a href="..\ntifs\nf-ntifs-cccaniwrite.md">CcCanIWrite</a>.

To cache a file, use <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.

The context parameters passed to <i>PostRoutine</i> are typically the I/O request and related context data.

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
<a href="..\ntifs\nf-ntifs-cccaniwrite.md">CcCanIWrite</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccsetdirtypagethreshold.md">CcSetDirtyPageThreshold</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcDeferWrite routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>