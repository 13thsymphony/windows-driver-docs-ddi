---
UID : NF:ntifs.CcFlushCache
title : CcFlushCache function
author : windows-driver-content
description : The CcFlushCache routine flushes all or a portion of a cached file to disk.
old-location : ifsk\ccflushcache.htm
old-project : ifsk
ms.assetid : 06bb49bc-56e6-42fc-ae52-c954507d2a3f
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : CcFlushCache
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
req.alt-api : CcFlushCache
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


# CcFlushCache function
The <b>CcFlushCache</b> routine flushes all or a portion of a cached file to disk.

## Syntax

````
VOID CcFlushCache(
  _In_      PSECTION_OBJECT_POINTERS SectionObjectPointer,
  _In_opt_  PLARGE_INTEGER           FileOffset,
  _In_      ULONG                    Length,
  _Out_opt_ PIO_STATUS_BLOCK         IoStatus
);
````

## Parameters

`SectionObjectPointer`

Pointer to a <b>SECTION_OBJECT_POINTERS</b> structure containing the file object's section object pointers.

`FileOffset`

Pointer to a variable that specifies the starting byte offset within the cached file where the data is to be flushed. 

If <i>FileOffset</i> is <b>NULL</b>, the entire file is flushed from the cache.

If <i>FileOffset</i> is not <b>NULL</b>, only the byte range specified by <i>FileOffset</i> and <i>Length</i> is flushed.

`Length`

Length of the byte range to flush, starting at <i>FileOffset</i>. If <i>FileOffset</i> is <b>NULL</b>, <i>Length</i> is ignored.

`IoStatus`

Pointer to a structure that receives the final completion status and information about the flush operation. If the data is flushed successfully, <i>IoStatus.Status</i> contains STATUS_SUCCESS. If not all of the data is flushed successfully, <i>IoStatus.Information</i> contains the actual number of bytes that were flushed. Otherwise, <i>IoStatus.Information</i> contains the value  given in <i>Length</i>.


## Return Value

None

## Remarks

<b>CcFlushCache</b> has no <i>Wait</i> parameter. Thus the caller must be able to enter a wait state until all the data has been flushed.

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
<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539143">CcIsFileCached</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpurgecachesection.md">CcPurgeCacheSection</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcFlushCache routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>