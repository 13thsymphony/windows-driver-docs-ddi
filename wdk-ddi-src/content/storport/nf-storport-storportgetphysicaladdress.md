---
UID: NF:storport.StorPortGetPhysicalAddress
title: StorPortGetPhysicalAddress function
author: windows-driver-content
description: The StorPortGetPhysicalAddress routine converts a given virtual address range to a physical address range for a DMA operation.
old-location: storage\storportgetphysicaladdress.htm
old-project: storage
ms.assetid: 2b39a6e4-2e11-4b4e-9218-92336629ae80
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortGetPhysicalAddress, StorPortGetPhysicalAddress routine [Storage Devices], storage.storportgetphysicaladdress, storport/StorPortGetPhysicalAddress, storprt_fea6d754-844c-4ee9-8153-97f2f0e9ee80.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortGetPhysicalAddress
product:
- Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortGetPhysicalAddress function
The <b>StorPortGetPhysicalAddress</b> routine converts a given virtual address range to a physical address range for a DMA operation.

## Syntax

```
STORPORT_API STOR_PHYSICAL_ADDRESS StorPortGetPhysicalAddress(
  PVOID               HwDeviceExtension,
  PSCSI_REQUEST_BLOCK Srb,
  PVOID               VirtualAddress,
  ULONG               *Length
);
```

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the device object for the HBA immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

`Srb`

Pointer to the SCSI request block if the virtual address to be converted comes from that SRB's <b>DataBuffer</b> member or <b>SenseInfoBuffer</b> member. Otherwise, this parameter must be <b>NULL</b>.

`VirtualAddress`

Pointer to the base virtual address to be converted. If this virtual address falls within the range for an SRB-supplied <b>DataBuffer</b>, the caller also must provide the <i>Srb</i> pointer.

`Length`

Pointer to a value indicating the number of bytes mapped, starting at the returned physical address.


## Return Value

<b>StorPortGetPhysicalAddress</b> returns the corresponding physical address for a given virtual address. If the given address cannot be converted, the function returns <b>NULL</b>.

## Remarks

If the virtual address passed to <b>StorPortGetPhysicalAddress</b> is obtained from <a href="https://msdn.microsoft.com/library/windows/hardware/ff567027">StorPortAllocateContiguousMemorySpecifyCacheNode</a>, the value returned for <i>Length</i> should be ignored.

Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.

<b>StorPortGetPhysicalAddress</b> uses <b>STOR_PHYSICAL_ADDRESS</b> to represent physical addresses.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef PHYSICAL_ADDRESS STOR_PHYSICAL_ADDRESS, *PSTOR_PHYSICAL_ADDRESS;
</pre>
</td>
</tr>
</table></span></div>
The <b>STOR_PHYSICAL_ADDRESS</b> type is an operating system-independent data type that Storport miniport drivers use to represent either a physical addresses or a bus-relative address.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564636">ScsiPortGetPhysicalAddress</a>