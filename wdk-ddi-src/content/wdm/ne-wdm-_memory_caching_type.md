---
UID: NE:wdm._MEMORY_CACHING_TYPE
title: _MEMORY_CACHING_TYPE
author: windows-driver-content
description: The MEMORY_CACHING_TYPE enumeration type specifies the permitted caching behavior when allocating or mapping memory.
old-location: kernel\memory_caching_type.htm
old-project: kernel
ms.assetid: 14cde545-e9bb-4b96-ba10-a63595e8a107
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _MEMORY_CACHING_TYPE, MEMORY_CACHING_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MEMORY_CACHING_TYPE
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (See Remarks section)
req.typenames: MEMORY_CACHING_TYPE
req.product: Windows 10 or later.
---

# _MEMORY_CACHING_TYPE enumeration



## -description
The <b>MEMORY_CACHING_TYPE</b> enumeration type specifies the permitted caching behavior when allocating or mapping memory.



## -syntax

````
typedef enum _MEMORY_CACHING_TYPE { 
  MmNonCached               = 0,
  MmCached                  = 1,
  MmWriteCombined           = 2,
  MmHardwareCoherentCached  = 3,
  MmNonCachedUnordered      = 4,
  MmUSWCCached              = 5,
  MmMaximumCacheType        = 6
} MEMORY_CACHING_TYPE;
````


## -enum-fields

### -field MmNonCached

The requested memory should not be cached by the processor.


### -field MmCached

The processor should cache the requested memory.


### -field MmWriteCombined

The requested memory should not be cached by the processor, but writes to the memory can be combined by the processor.


### -field MmHardwareCoherentCached

Reserved for system use.


### -field MmNonCachedUnordered

Reserved for system use.


### -field MmUSWCCached

Reserved for system use.


### -field MmMaximumCacheType

Reserved for system use.


## -remarks
Processor translation buffers cache virtual to physical address translations. These translation buffers allow many virtual addresses to map a single physical address. However, only one caching behavior is allowed for any given physical address translation. Therefore, if a driver maps two different virtual address ranges to the same physical address, it must ensure that it specifies the same caching behavior for both. Otherwise, the processor behavior is undefined with unpredictable system results.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in Windows 2000 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Ntddk.h or Wdm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-mmallocatecontiguousmemoryspecifycache.md">MmAllocateContiguousMemorySpecifyCache</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-mmfreecontiguousmemoryspecifycache.md">MmFreeContiguousMemorySpecifyCache</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-mmmapiospace.md">MmMapIoSpace</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-mmmaplockedpageswithreservedmapping.md">MmMapLockedPagesWithReservedMapping</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MEMORY_CACHING_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

