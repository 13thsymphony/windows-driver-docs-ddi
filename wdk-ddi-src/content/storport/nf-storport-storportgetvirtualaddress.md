---
UID: NF:storport.StorPortGetVirtualAddress
title: StorPortGetVirtualAddress function
author: windows-driver-content
description: The StorPortGetVirtualAddress routine obtains a virtual address that maps to the indicated physical address.
old-location: storage\storportgetvirtualaddress.htm
old-project: storage
ms.assetid: b7091dea-8a29-4ad3-a478-29bc28fd57ef
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: StorPortGetVirtualAddress, StorPortGetVirtualAddress routine [Storage Devices], storage.storportgetvirtualaddress, storport/StorPortGetVirtualAddress, storprt_5245f704-dce0-4683-8510-064ccbb4158c.xml
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
-	StorPortGetVirtualAddress
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortGetVirtualAddress function
The <b>StorPortGetVirtualAddress</b> routine obtains a virtual address that maps to the indicated physical address.

## Syntax

````
STORPORT_API PVOID StorPortGetVirtualAddress(
  _In_ PVOID                 HwDeviceExtension,
  _In_ STOR_PHYSICAL_ADDRESS PhysicalAddress
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

`PhysicalAddress`

Specifies the physical address to be mapped. This value must have been returned by <a href="..\storport\nf-storport-storportgetphysicaladdress.md">StorPortGetPhysicalAddress</a> and must be from an uncached device extension or SRB extension.


## Return Value

<b>StorPortGetVirtualAddress</b> returns a virtual address associated with the physical address indicated in the <i>PhysicalAddress</i> parameter. Typically, this physical address was obtained by a call to <a href="..\storport\nf-storport-storportgetphysicaladdress.md">StorPortGetPhysicalAddress</a>.

## Remarks

The physical address must be an address that is obtained through a call to <a href="..\storport\nf-storport-storportgetphysicaladdress.md">StorPortGetPhysicalAddress</a>.

<b>StorPortGetVirtualAddress</b> uses <b>STOR_PHYSICAL_ADDRESS</b> to represent physical addresses.

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

<a href="..\srb\nf-srb-scsiportgetvirtualaddress.md">ScsiPortGetVirtualAddress</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetVirtualAddress routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>