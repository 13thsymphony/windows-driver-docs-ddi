---
UID : NF:ntifs.CcSetDirtyPageThreshold
title : CcSetDirtyPageThreshold function
author : windows-driver-content
description : The CcSetDirtyPageThreshold routine sets a per-file dirty page threshold on a cached file.
old-location : ifsk\ccsetdirtypagethreshold.htm
old-project : ifsk
ms.assetid : ba7023d9-5130-4eea-9de9-034f5bf0b145
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : CcSetDirtyPageThreshold
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
req.alt-api : CcSetDirtyPageThreshold
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


# CcSetDirtyPageThreshold function
The <b>CcSetDirtyPageThreshold</b> routine sets a per-file dirty page threshold on a cached file.

## Syntax

````
VOID CcSetDirtyPageThreshold(
  _In_ PFILE_OBJECT FileObject,
  _In_ ULONG        DirtyPageThreshold
);
````

## Parameters

`FileObject`

Pointer to a file object for the cached file on which the dirty page threshold is to be set.

`DirtyPageThreshold`

Specifies, as a number of pages, the dirty page threshold value. To remove a per-file dirty page threshold value that was set previously, set <i>DirtyPageThreshold</i> to zero.


## Return Value

None

## Remarks

<b>CcSetDirtyPageThreshold</b> sets or removes a per-file dirty page threshold. After a per-file dirty page threshold is set on a cached file, if the file system attempts to exceed the threshold, the cache manager will refuse requests to write to the file.

To determine whether the cache manager will accept or refuse write requests, use <a href="..\ntifs\nf-ntifs-cccaniwrite.md">CcCanIWrite</a>.

Note that the <i>per-file</i> dirty page threshold is not the same as the <i>global</i> dirty page threshold for the entire system cache.

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
<a href="..\ntifs\nf-ntifs-ccdeferwrite.md">CcDeferWrite</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcSetDirtyPageThreshold routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>