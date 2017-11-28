---
UID: NS.ndis._NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
title: NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
author: windows-driver-content
description: The NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure specifies shared memory provider characteristics.
old-location: netvista\ndis_shared_memory_provider_characteristics.htm
old-project: netvista
ms.assetid: 45001da1-5fe3-4383-8da7-31e3ee115c1f
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, *PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.iface: 
---

# NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure



## -description
<p>The NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure specifies shared memory provider
  characteristics.</p>


## -syntax

````
typedef struct _NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS {
  NDIS_OBJECT_HEADER             Header;
  ULONG                          Flags;
  NDIS_HANDLE                    ProviderContext;
  ALLOCATE_SHARED_MEMORY_HANDLER AllocateSharedMemoryHandler;
  FREE_SHARED_MEMORY_HANDLER     FreeSharedMemoryHandler;
} NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, *PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     structure (NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_SHARED_MEMORY_PROVIDER_CHARACTERISTICS_REVISION_1.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Reserved for NDIS.</p>
</dd>

### -field <b>ProviderContext</b>

<dd>
<p>An NDIS_HANDLE to a block of driver-allocated context information that stores information about
     the provider. NDIS passes the context information in calls to 
     <i>NetXxxSharedMemory</i> functions at the 
     <i>ProviderContext</i> parameter.</p>
</dd>

### -field <b>AllocateSharedMemoryHandler</b>

<dd>
<p>An entry point for the 
     <a href="..\ndis\nc-ndis-allocate-shared-memory-handler.md">
     NetAllocateSharedMemory</a> function.</p>
</dd>

### -field <b>FreeSharedMemoryHandler</b>

<dd>
<p>An entry point for the 
     <a href="..\ndis\nc-ndis-free-shared-memory-handler.md">NetFreeSharedMemory</a> function.</p>
</dd>
</dl>

## -remarks
<p>To specify entry points for shared memory services, an NDIS driver initializes an
    NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure and passes it to the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">
    NdisSetOptionalHandlers</a> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.20 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-allocate-shared-memory-handler.md">NetAllocateSharedMemory</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-free-shared-memory-handler.md">NetFreeSharedMemory</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
