---
UID: NC.dispmprt.DXGKCB_AGP_FREE_POOL
title: DXGKCB_AGP_FREE_POOL
author: windows-driver-content
description: The AgpFreePool function frees AGP memory that was previously allocated by AgpAllocatePool.
old-location: display\agpfreepool.htm
old-project: display
ms.assetid: 6d4e957e-ad9c-45da-8d1d-0ef5f108c692
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
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
req.alt-api: AgpFreePool
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

# DXGKCB_AGP_FREE_POOL callback



## -description
The <b>AgpFreePool</b> function frees AGP memory that was previously allocated by <a href="..\dispmprt\nc-dispmprt-dxgkcb_agp_allocate_pool.md">AgpAllocatePool</a>.


## -prototype

````
DXGKCB_AGP_FREE_POOL AgpFreePool;

NTSTATUS APIENTRY AgpFreePool(
  _In_ HANDLE Context,
  _In_ PVOID  VirtualAddress
)
{ ... }
````


## -parameters

### -param Context [in]

A handle to a context block that is associated with an AGP interface. The display miniport driver previously received this handle in the <b>Context</b> member of the DXGK_AGP_INTERFACE structure that was filled in by <a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a>.

### -param VirtualAddress [in]

The base virtual address of the AGP allocation that is to be freed. This is the virtual address that was previously returned in the <i>VirtualAddress</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkcb_agp_allocate_pool.md">AgpAllocatePool</a> function.

## -returns
<b>AgpFreePool</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## -remarks
None.

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
<a href="..\dispmprt\nc-dispmprt-dxgkcb_agp_allocate_pool.md">AgpAllocatePool</a>
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
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_AGP_FREE_POOL callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
