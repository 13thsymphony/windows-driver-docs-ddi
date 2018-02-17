---
UID: NC:dispmprt.DXGKCB_MAP_MEMORY
title: DXGKCB_MAP_MEMORY
author: windows-driver-content
description: The DxgkCbMapMemory function maps a range of translated physical addresses (associated with a memory resource assigned to a display adapter) into system space or the virtual address space of a user-mode process.
old-location: display\dxgkcbmapmemory.htm
old-project: display
ms.assetid: 916a4d1d-0c40-4125-89ae-488251b04810
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbmapmemory, DxgkCbMapMemory callback function [Display Devices], DxgkCbMapMemory, DXGKCB_MAP_MEMORY, DXGKCB_MAP_MEMORY, dispmprt/DxgkCbMapMemory, DpFunctions_51d99a74-2fae-40b7-9e04-8afe0fc38805.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkCbMapMemory
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---


# DXGKCB_MAP_MEMORY callback function
The <b>DxgkCbMapMemory</b> function maps a range of translated physical addresses (associated with a memory resource assigned to a display adapter) into system space or the virtual address space of a user-mode process.

## Syntax

```
DXGKCB_MAP_MEMORY DxgkcbMapMemory;

NTSTATUS DxgkcbMapMemory(
  HANDLE DeviceHandle,
  PHYSICAL_ADDRESS TranslatedAddress,
  ULONG Length,
  BOOLEAN InIoSpace,
  BOOLEAN MapToUserMode,
  MEMORY_CACHING_TYPE CacheType,
  PVOID *VirtualAddress
)
{...}
```

## Parameters

`DeviceHandle`

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.

`TranslatedAddress`

The base translated physical address of the memory range to be mapped. The display miniport driver previously obtained this address by calling <a href="..\dispmprt\nc-dispmprt-dxgkcb_get_device_information.md">DxgkCbGetDeviceInformation</a>.

`Length`

The size, in bytes, of the range to be mapped.

`InIoSpace`

A Boolean value that specifies whether the range is in I/O space (<b>TRUE</b>) or memory space (<b>FALSE</b>).

`MapToUserMode`

A Boolean value that specifies whether the range is mapped into user-mode space or system space. If <b>TRUE</b>, the range is mapped into the (user-mode) virtual address space of the current process. If <b>FALSE</b>, the range is mapped into system space. If <i>InIoSpace</i> is <b>TRUE</b>, this parameter is ignored.

`CacheType`

A <a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a> enumerator that specifies the caching behavior of the mapped range.

`*VirtualAddress`

A pointer to a variable that receives the address of the beginning of the mapped range. The way that the mapped range is accessed depends on the values of <i>InIoSpace</i> and <i>MapToUserMode</i>. The following table summarizes the different ways that the mapped range is accessed.

<table>
<tr>
<td></td>
<td><i>MapToUserMode</i> is <b>FALSE</b></td>
<td><i>MapToUserMode</i> is <b>TRUE</b></td>
</tr>
<tr>
<td><i>InIoSpace</i> is <b>FALSE</b></td>
<td>READ_REGISTER_X WRITE_REGISTER_X</td>
<td>User-mode code performs ordinary memory access.</td>
</tr>
<tr>
<td><i>InIoSpace</i> is <b>TRUE</b></td>
<td>READ_PORT_X WRITE_PORT_X</td>
<td>Not possible.</td>
</tr>
</table>


## Return Value

<b>DxgkCbMapMemory</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## Remarks

The PHYSICAL_ADDRESS data type is defined in <i>Ntdef.h</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_MAP_MEMORY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>