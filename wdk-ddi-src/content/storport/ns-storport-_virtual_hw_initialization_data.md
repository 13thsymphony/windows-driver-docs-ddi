---
UID: NS:storport._VIRTUAL_HW_INITIALIZATION_DATA
title: "_VIRTUAL_HW_INITIALIZATION_DATA"
author: windows-driver-content
description: The VIRTUAL_HW_INITIALIZATION_DATA structure contains information particular to each virtual miniport driver.
old-location: storage\virtual_hw_initialization_data.htm
old-project: storage
ms.assetid: 10e7e097-ed84-4200-b7b6-6a838a058fd2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.virtual_hw_initialization_data, storport/PVIRTUAL_HW_INITIALIZATION_DATA, VIRTUAL_HW_INITIALIZATION_DATA structure [Storage Devices], storport/VIRTUAL_HW_INITIALIZATION_DATA, VIRTUAL_HW_INITIALIZATION_DATA, PVIRTUAL_HW_INITIALIZATION_DATA structure pointer [Storage Devices], structs-virtual_afc3c543-a34f-4853-b67b-06d57d0350b6.xml, PVIRTUAL_HW_INITIALIZATION_DATA, _VIRTUAL_HW_INITIALIZATION_DATA, *PVIRTUAL_HW_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	VIRTUAL_HW_INITIALIZATION_DATA
product: Windows
targetos: Windows
req.typenames: "*PVIRTUAL_HW_INITIALIZATION_DATA, VIRTUAL_HW_INITIALIZATION_DATA"
req.product: Windows 10 or later.
---

# _VIRTUAL_HW_INITIALIZATION_DATA structure
The <b>VIRTUAL_HW_INITIALIZATION_DATA</b> structure contains information particular to each virtual miniport driver.

## Syntax
````
typedef struct _VIRTUAL_HW_INITIALIZATION_DATA {
  ULONG                       HwInitializationDataSize;
  INTERFACE_TYPE              AdapterInterfaceType;
  PHW_INITIALIZE              HwInitialize;
  PHW_STARTIO                 HwStartIo;
  PHW_INTERRUPT               HwInterrupt;
  PVIRTUAL_HW_FIND_ADAPTER    HwFindAdapter;
  PHW_RESET_BUS               HwResetBus;
  PHW_DMA_STARTED             HwDmaStarted;
  PHW_ADAPTER_STATE           HwAdapterState;
  ULONG                       DeviceExtensionSize;
  ULONG                       SpecificLuExtensionSize;
  ULONG                       SrbExtensionSize;
  ULONG                       NumberOfAccessRanges;
  PVOID                       Reserved;
  UCHAR                       MapBuffers;
  BOOLEAN                     NeedPhysicalAddresses;
  BOOLEAN                     TaggedQueuing;
  BOOLEAN                     AutoRequestSense;
  BOOLEAN                     MultipleRequestPerLu;
  BOOLEAN                     ReceiveEvent;
  USHORT                      VendorIdLength;
  PVOID                       VendorId;
  union {
    USHORT ReservedUshort;
    USHORT PortVersionFlags;
  };
  USHORT                      DeviceIdLength;
  PVOID                       DeviceId;
  PHW_ADAPTER_CONTROL         HwAdapterControl;
  PHW_BUILDIO                 HwBuildIo;
  PHW_FREE_ADAPTER_RESOURCES  HwFreeAdapterResources;
  PHW_PROCESS_SERVICE_REQUEST HwProcessServiceRequest;
  PHW_COMPLETE_SERVICE_IRP    HwCompleteServiceIrp;
  PHW_INITIALIZE_TRACING      HwInitializeTracing;
  PHW_CLEANUP_TRACING         HwCleanupTracing;
} VIRTUAL_HW_INITIALIZATION_DATA, *PVIRTUAL_HW_INITIALIZATION_DATA;
````

## Members


`AdapterInterfaceType`

The Storport driver does not support legacy buses. Therefore, most of the adapter interface types that are used with the SCSI port driver are invalid for Storport drivers. In particular, Storport does not support Isa, Eisa, MicroChannel, and TurboChannel. Furthermore, unlike the SCSI port case, a virtual miniport driver that works with the Storport driver is not required to supply values for the <b>VendorIdLength</b>, <b>VendorId</b>, <b>DeviceIdLength</b>, and <b>DeviceId</b> members.

`AutoRequestSense`

Must be set to <b>TRUE</b>. A value of <b>TRUE</b> indicates that the HBA can perform a request-sense operation without requiring an explicit request to do so.

`DeviceExtensionSize`

Specifies the size, in bytes, that is required by the virtual miniport driver for its per-adapter non-paged device extension. A virtual miniport driver uses its device extension as storage for driver-determined adapter information. The operating system-specific port driver initializes each device extension that it allocates with zeros, and passes a pointer to the adapter-specific device extension in most calls to the virtual miniport driver. The given size does not include any virtual miniport driver-requested per-logical-unit storage.

`DeviceId`

The device identifier.

`DeviceIdLength`

The length, in bytes, of the device identifier.

`HwAdapterControl`

A pointer to the virtual miniport driver's <a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a> routine.

`HwAdapterState`

The Storport driver does not support legacy drivers. Therefore, this member must be <b>NULL</b>.

`HwBuildIo`

This member is not used.

`HwCleanupTracing`

A pointer to the virtual miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557372">HwStorCleanupTracing</a> routine.

`HwCompleteServiceIrp`

A pointer to the virtual miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557379">HwStorCompleteServiceIrp</a> routine.

`HwDmaStarted`

Not used. Virtual miniport drivers do not perform DMA.

`HwFindAdapter`

A pointer to the virtual miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568008">VirtualHwStorFindAdapter</a> routine, which is a required entry point for all virtual miniport drivers.

`HwFreeAdapterResources`

A pointer to the virtual miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557392">HwStorFreeAdapterResources</a> routine, which is a required entry point for all virtual miniport drivers.

`HwInitializationDataSize`

Specifies the size of this structure in bytes, as returned by <b>sizeof</b>(). This member indicates the version of this structure that is used by the virtual miniport driver. A virtual miniport driver's <b>DriverEntry</b> routine should set this member's value for the port driver.

`HwInitialize`

A pointer to the virtual miniport driver's <a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a> routine, which is a required entry point for all virtual miniport drivers.

`HwInitializeTracing`

A pointer to the virtual miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557402">HwStorInitializeTracing</a> routine.

`HwInterrupt`

Not used. Virtual miniport drivers do not process interrupts.

`HwProcessServiceRequest`

A pointer to the virtual miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557410">HwStorProcessServiceRequest</a> routine.

`HwResetBus`

A pointer to the virtual miniport driver's <a href="..\storport\nc-storport-hw_reset_bus.md">HwStorResetBus</a> routine, which is a required entry point for all virtual miniport drivers.

`HwStartIo`

A pointer to the virtual miniport driver's <a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a> routine, which is a required entry point for all virtual miniport drivers.

`MapBuffers`

Not valid for virtual miniport drivers. The virtual miniport driver must map all data buffers into virtual address space.

`MultipleRequestPerLu`

Must be set to <b>TRUE</b>. A value of <b>TRUE</b> indicates that the virtual miniport driver can queue multiple requests per logical unit (LU).

`NeedPhysicalAddresses`

Not used. Virtual miniport drivers do not support hardware.

`NumberOfAccessRanges`

Not used. Virtual miniport drivers do not support hardware.

`ReceiveEvent`

Must be set to <b>TRUE</b>. A value of <b>TRUE</b> indicates that the virtual miniport driver supports receive events.

`Reserved`

Reserved for system use.

`SpecificLuExtensionSize`

Specifies the size, in bytes, that is required by the virtual miniport driver for its per-logical-unit non-paged storage, if any. A virtual miniport driver can use its logical unit (LU) extensions as storage for driver-determined LU information about peripherals on the virtual bus. The operating system-specific port driver initializes each LU extension that it allocates with zeros. Leave this member set to zero if the virtual miniport driver does not maintain per-LU information for which it requires storage.

`SrbExtensionSize`

Specifies the size, in bytes, that is required by the virtual miniport driver for its per-request non-paged storage, if any. Because virtual miniport drivers that work with the Storport driver must support scatter/gather lists, and the per-SRB scatter/gather lists are usually allocated in the SRB extension, this member is rarely zero.

`TaggedQueuing`

Must be set to <b>TRUE</b>. A value of <b>TRUE</b> indicates that the virtual miniport driver supports tagged queuing.

`VendorId`

The vendor identifier.

`VendorIdLength`

The length, in bytes, of the vendor identifier.

## Remarks
If a virtual miniport driver will execute only on Windows 8 or later, the driver should use the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure instead of <b>VIRTUAL_HW_INITIALIZATION_DATA</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | storport.h (include Storport.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557402">HwStorInitializeTracing</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557410">HwStorProcessServiceRequest</a>

<a href="..\storport\nc-storport-hw_reset_bus.md">HwStorResetBus</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568008">VirtualHwStorFindAdapter</a>

<a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557392">HwStorFreeAdapterResources</a>

<a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557372">HwStorCleanupTracing</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557379">HwStorCompleteServiceIrp</a>

<a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20VIRTUAL_HW_INITIALIZATION_DATA structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>