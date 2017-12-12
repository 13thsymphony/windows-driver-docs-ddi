---
UID: NC.dispmprt.DXGKCB_AGP_ALLOCATE_POOL
title: DXGKCB_AGP_ALLOCATE_POOL
author: windows-driver-content
description: The AgpAllocatePool function reserves, commits, and maps AGP memory.
old-location: display\agpallocatepool.htm
old-project: display
ms.assetid: abac76e0-eb8a-450a-a797-3733a8f71990
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SYMBOL_INFO_EX, *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AgpAllocatePool
req.alt-loc: dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# DXGKCB_AGP_ALLOCATE_POOL callback



## -description
The <b>AgpAllocatePool</b> function reserves, commits, and maps AGP memory.



## -prototype

````
DXGKCB_AGP_ALLOCATE_POOL AgpAllocatePool;

NTSTATUS APIENTRY AgpAllocatePool(
  _In_  HANDLE              Context,
  _In_  ULONG               AllocationSize,
  _In_  MEMORY_CACHING_TYPE CacheType,
  _Out_ PPHYSICAL_ADDRESS   PhysicalAddress,
  _Out_ PVOID               *VirtualAddress
)
{ ... }
````


## -parameters

### -param Context [in]

A handle to a context block associated with an AGP interface. The display miniport driver previously received this handle in the <b>Context</b> member of the DXGK_AGP_INTERFACE structure that was filled in by <a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a>.


### -param AllocationSize [in]

The size, in bytes, of the AGP memory to be allocated.


### -param CacheType [in]

A constant from the <a href="kernel.memory_caching_type">MEMORY_CACHING_TYPE</a> enumeration that specifies whether the CPU can use caching or write combining when it accesses the allocated AGP memory.


### -param PhysicalAddress [out]

A pointer to a PHYSICAL_ADDRESS structure that receives the base physical address of the AGP allocation. This is the base of the physical address range that the GPU will use to access the AGP memory.


### -param VirtualAddress [out]

A pointer to a variable that receives the base virtual address, in system space, of the AGP allocation. This is the base of the virtual address range that the CPU will use to access the AGP memory.


## -returns
<b>AgpAllocatePool</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.


## -remarks
Call <b>AgpAllocatePool</b> in the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function. It is likely that <b>AgpAllocatePool</b> will fail if you call it after <b>DxgkDdiStartDevice</b> has executed.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb_agp_free_pool.md">AgpFreePool</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb_agp_set_command.md">AgpSetCommand</a>
</dt>
<dt>
<a href="display.dxgk_agp_interface">DXGK_AGP_INTERFACE</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_AGP_ALLOCATE_POOL callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

