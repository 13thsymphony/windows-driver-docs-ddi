---
UID: NF:wdm.RtlPrefetchMemoryNonTemporal
title: RtlPrefetchMemoryNonTemporal function
author: windows-driver-content
description: The RtlPrefetchMemoryNonTemporal routine provides a hint to the processor that a buffer should be temporarily moved into the processor cache.
old-location: kernel\rtlprefetchmemorynontemporal.htm
old-project: kernel
ms.assetid: d11c3414-86c8-4b68-829e-4523519c5299
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlPrefetchMemoryNonTemporal
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlPrefetchMemoryNonTemporal
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlPrefetchMemoryNonTemporal function



## -description
The <b>RtlPrefetchMemoryNonTemporal</b> routine provides a hint to the processor that a buffer should be temporarily moved into the processor cache.



## -syntax

````
VOID RtlPrefetchMemoryNonTemporal(
  _In_ PVOID  Source,
  _In_ SIZE_T Length
);
````


## -parameters

### -param Source [in]

A pointer to the buffer to be moved into the processor cache. 


### -param Length [in]

The length of the buffer to be moved. 


## -returns
None.


## -remarks
You should use this routine only for a buffer that will be written to or read from exactly once. Note that <b>RtlPrefetchMemoryNonTemporal</b> is only a hint to the processor: the buffer is not guaranteed to be moved into the cache. On x86-based and x64-based systems, this routine uses the <b>prefetchnta</b> instruction.</p>