---
UID : NF:ntifs.CcSetReadAheadGranularity
title : CcSetReadAheadGranularity function
author : windows-driver-content
description : The CcSetReadAheadGranularity routine sets the read-ahead granularity for a cached file.
old-location : ifsk\ccsetreadaheadgranularity.htm
old-project : ifsk
ms.assetid : 3ab0c8b8-1f41-48b7-9c42-ea843ebcd82e
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ifsk.ccsetreadaheadgranularity, CcSetReadAheadGranularity, CcSetReadAheadGranularity routine [Installable File System Drivers], ccref_9b995224-0e59-43c6-b827-c15d9ae6e86c.xml, ntifs/CcSetReadAheadGranularity
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# CcSetReadAheadGranularity function
The <b>CcSetReadAheadGranularity</b> routine sets the read-ahead granularity for a cached file.

## Syntax

````
VOID CcSetReadAheadGranularity(
  _In_ PFILE_OBJECT FileObject,
  _In_ ULONG        Granularity
);
````

## Parameters

`FileObject`

Pointer to a file object for the cached file whose read-ahead granularity is to be set.

`Granularity`

Specifies the desired read-ahead granularity, which must be an even power of two and must be greater than or equal to PAGE_SIZE.


## Return Value

None

## Remarks

After <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a> is called to cache a file, but before <b>CcSetReadAheadGranularity</b> is called for the cached file, the default read-ahead granularity for the cached file is equal to PAGE_SIZE.

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

<a href="..\ntifs\nf-ntifs-ccschedulereadahead.md">CcScheduleReadAhead</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539191">CcReadAhead</a>

<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>

<a href="..\ntifs\nf-ntifs-ccsetadditionalcacheattributes.md">CcSetAdditionalCacheAttributes</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcSetReadAheadGranularity routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>