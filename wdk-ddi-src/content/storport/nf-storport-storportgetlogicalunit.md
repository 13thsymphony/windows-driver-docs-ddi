---
UID: NF:storport.StorPortGetLogicalUnit
title: StorPortGetLogicalUnit function
author: windows-driver-content
description: The StorPortGetLogicalUnit routine returns a pointer to the miniport driver's per-logical-unit storage area.
old-location: storage\storportgetlogicalunit.htm
old-project: storage
ms.assetid: c8972d8b-9eba-4276-af63-1096a76b104f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortGetLogicalUnit, StorPortGetLogicalUnit routine [Storage Devices], storage.storportgetlogicalunit, storport/StorPortGetLogicalUnit, storprt_065c9617-06c6-4795-9743-14cd5803d9f9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
-	StorPortGetLogicalUnit
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortGetLogicalUnit function
The <b>StorPortGetLogicalUnit</b> routine returns a pointer to the miniport driver's per-logical-unit storage area.

## Syntax

```
STORPORT_API PVOID StorPortGetLogicalUnit(
  PVOID HwDeviceExtension,
  UCHAR PathId,
  UCHAR TargetId,
  UCHAR Lun
);
```

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver as soon as the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557390">HwStorFindAdapter</a> routine is called. The port driver frees this memory when it removes the device.

`PathId`

Identifies the SCSI bus.

`TargetId`

Identifies the target controller or device on the bus.

`Lun`

Identifies the logical unit (LU) number of the target device.


## Return Value

<b>StorPortGetLogicalUnit</b> returns a pointer to the miniport driver's storage area for the requested logical unit. If the logical unit does not exist, it returns <b>NULL</b>.

## Remarks

<b>StorPortGetLogicalUnit</b> is irrelevant if the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine specified zero for the <b>LuExtensionSize</b> in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> when it called <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. Otherwise, the operating system-specific port driver allocates and initializes with zeros a set of LU extensions of the specified size for the miniport driver to use.

Per-LU storage can be used to store data relevant to a particular peripheral, such as saved data pointers. To access this area, the miniport driver calls <b>StorPortGetLogicalUnit</b> when the driver is maintaining information about the state of or current operation for any particular peripheral.

The operating system-specific port driver can consider a logical unit to be nonexistent if there is no active request for that logical unit and the device has never been successfully selected.

<div class="alert"><b>Note</b>  When the miniport driver calls <b>StorPortGetLogicalUnit</b> at IRQL = DISPATCH_LEVEL, the function acquires the interrupt lock. Calling <b>StorPortGetLogicalUnit</b> too often at this IRQL level impacts the performance and scalability of the miniport driver.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>