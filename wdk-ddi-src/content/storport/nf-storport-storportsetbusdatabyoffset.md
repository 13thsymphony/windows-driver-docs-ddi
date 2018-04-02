---
UID: NF:storport.StorPortSetBusDataByOffset
title: StorPortSetBusDataByOffset function
author: windows-driver-content
description: The StorPortSetBusDataByOffset routine writes bus-specific configuration information.
old-location: storage\storportsetbusdatabyoffset.htm
old-project: storage
ms.assetid: ec1db013-b630-421b-8d22-385a2d9b9510
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortSetBusDataByOffset, StorPortSetBusDataByOffset routine [Storage Devices], storage.storportsetbusdatabyoffset, storport/StorPortSetBusDataByOffset, storprt_ebb2afc1-b190-4674-8ee7-bd61953565ab.xml
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
-	StorPortSetBusDataByOffset
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortSetBusDataByOffset function
The <b>StorPortSetBusDataByOffset</b> routine writes bus-specific configuration information.

## Syntax

```
STORPORT_API ULONG StorPortSetBusDataByOffset(
  PVOID DeviceExtension,
  ULONG BusDataType,
  ULONG SystemIoBusNumber,
  ULONG SlotNumber,
  PVOID Buffer,
  ULONG Offset,
  ULONG Length
);
```

## Parameters

`DeviceExtension`

Pointer to the miniport driver's per-HBA storage area.

`BusDataType`

Contains a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff540700">BUS_DATA_TYPE</a> that specifies the type of the bus for which configuration information is to be written. Currently, its value can be <b>PCIConfiguration</b>. However, additional types of standardized, dynamically configurable buses will be supported in future. The upper bound on the bus types supported is always <b>MaximumBusDataType</b>.

`SystemIoBusNumber`

Specifies the system-assigned number of the I/O bus on which the HBA is connected. The miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557390">HwStorFindAdapter</a> routine obtains this value from the input <b>PORT_CONFIGURATION_INFORMATION</b><b>SystemIoBusNumber</b> member.

`SlotNumber`

Indicates the logical slot number of the HBA.

When <b>PCIConfiguration</b> is specified as the <i>BusDataType</i>, this parameter must be specified as a PCI_SLOT_NUMBER-type value.

`Buffer`

Pointer to a caller-supplied storage area with configuration information specific to <i>BusDataType</i>. 

When <b>PCIConfiguration</b> is specified, the buffer contains some or all of the PCI_COMMON_CONFIG information for the given <i>SlotNumber</i>. The specified <i>Offset</i> and <i>Length</i> determine how much information is supplied.

`Offset`

Specifies the byte offset within the PCI_COMMON_CONFIG structure at which the caller-supplied configuration values begin. A miniport driver can use PCI_COMMON_HDR_LENGTH to specify the offset of the device-specific area in PCI_COMMON_CONFIG.

`Length`

Indicates the length, in bytes, of the maximum amount of data to return.


## Return Value

<b>StorPortSetBusDataByOffset</b> returns the number of bytes of configuration data written.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564751">ScsiPortSetBusDataByOffset</a>