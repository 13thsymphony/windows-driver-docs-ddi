---
UID: NS:wdm._PCI_SLOT_NUMBER
title: "_PCI_SLOT_NUMBER"
author: windows-driver-content
description: The PCI_SLOT_NUMBER structure is obsolete.
old-location: kernel\pci_slot_number.htm
old-project: kernel
ms.assetid: 0e04813d-e138-435e-8357-562f79a3a4a2
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPCI_SLOT_NUMBER, PCI_SLOT_NUMBER, PCI_SLOT_NUMBER structure [Kernel-Mode Driver Architecture], PPCI_SLOT_NUMBER, PPCI_SLOT_NUMBER structure pointer [Kernel-Mode Driver Architecture], _PCI_SLOT_NUMBER, kernel.pci_slot_number, kstruct_c_e9aa5e88-0c5d-4740-80f3-4b59da610598.xml, wdm/PCI_SLOT_NUMBER, wdm/PPCI_SLOT_NUMBER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	PCI_SLOT_NUMBER
product: Windows
targetos: Windows
req.typenames: PCI_SLOT_NUMBER, *PPCI_SLOT_NUMBER
req.product: Windows 10 or later.
---

# _PCI_SLOT_NUMBER structure
The <b>PCI_SLOT_NUMBER</b> structure is <u>obsolete</u>. It defines the format of the <i>Slot</i> parameter to the obsolete <b>Hal<i>Xxx</i>BusData</b> routines when they are called with the <i>BusDataType</i> value <b>PCIConfiguration</b>.

## Syntax
````
typedef struct _PCI_SLOT_NUMBER {
  union {
    struct {
      ULONG DeviceNumber  :5;
      ULONG FunctionNumber  :3;
      ULONG Reserved  :24;
    } bits;
    ULONG AsULONG;
  } u;
} PCI_SLOT_NUMBER, *PPCI_SLOT_NUMBER;
````

## Members


`u`

#### AsULONG

Specifies the logical slot number of the device being configured.

## Remarks
Drivers of PCI devices can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a> more than once for the same slot number to get the configuration information for their device(s).

For example, a driver might search for devices it supports on all PCI buses in the machine first, and then call <code>HalGetBusData(ByOffset)</code> again to request more configuration information about devices of interest. Such a driver could code a loop that calls <code>HalGetBusData(ByOffset)</code> with an input <code>Buffer</code> of sufficient <code>Length</code> only to contain enough of the <a href="..\wdm\ns-wdm-_pci_common_config.md">PCI_COMMON_CONFIG</a> to determine the <code>VendorID</code> and <code>DeviceID</code> of each PCI device. After finding the <code>Slot</code> numbers for any promising PCI devices, the driver would call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a> one or more times with additional buffer space to get the information needed to configure its devices.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Miniport.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>



<a href="..\wdm\ns-wdm-_pci_common_config.md">PCI_COMMON_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546628">HalSetBusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546633">HalSetBusDataByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546580">HalAssignSlotResources</a>