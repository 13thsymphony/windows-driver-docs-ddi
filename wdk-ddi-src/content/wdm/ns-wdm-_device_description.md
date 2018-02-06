---
UID: NS:wdm._DEVICE_DESCRIPTION
title: "_DEVICE_DESCRIPTION"
author: windows-driver-content
description: The DEVICE_DESCRIPTION structure describes the attributes of the physical device for which a driver is requesting a DMA adapter.
old-location: kernel\device_description.htm
old-project: kernel
ms.assetid: 7f0c7d72-9fe6-4cc1-8028-fd64cdee5d85
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "_DEVICE_DESCRIPTION, *PDEVICE_DESCRIPTION, wdm/DEVICE_DESCRIPTION, kstruct_a_22341019-dd23-41b3-b7d9-73a22ba1e146.xml, kernel.device_description, DEVICE_DESCRIPTION_VERSION, DEVICE_DESCRIPTION_VERSION3, DEVICE_DESCRIPTION, DEVICE_DESCRIPTION_VERSION2, wdm/PDEVICE_DESCRIPTION, PDEVICE_DESCRIPTION, DEVICE_DESCRIPTION structure [Kernel-Mode Driver Architecture], PDEVICE_DESCRIPTION structure pointer [Kernel-Mode Driver Architecture], DEVICE_DESCRIPTION_VERSION1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 2000.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	DEVICE_DESCRIPTION
product: Windows
targetos: Windows
req.typenames: "*PDEVICE_DESCRIPTION, DEVICE_DESCRIPTION"
req.product: Windows 10 or later.
---

# _DEVICE_DESCRIPTION structure
The <b>DEVICE_DESCRIPTION</b> structure describes the attributes of the physical device for which a driver is requesting a DMA adapter.

## Syntax
````
typedef struct _DEVICE_DESCRIPTION {
  ULONG            Version;
  BOOLEAN          Master;
  BOOLEAN          ScatterGather;
  BOOLEAN          DemandMode;
  BOOLEAN          AutoInitialize;
  BOOLEAN          Dma32BitAddresses;
  BOOLEAN          IgnoreCount;
  BOOLEAN          Reserved1;
  BOOLEAN          Dma64BitAddresses;
  ULONG            BusNumber;
  ULONG            DmaChannel;
  INTERFACE_TYPE   InterfaceType;
  DMA_WIDTH        DmaWidth;
  DMA_SPEED        DmaSpeed;
  ULONG            MaximumLength;
  ULONG            DmaPort;
  ULONG            DmaAddressWidth;
  ULONG            DmaControllerInstance;
  ULONG            DmaRequestLine;
  PHYSICAL_ADDRESS DeviceAddress;
} DEVICE_DESCRIPTION, *PDEVICE_DESCRIPTION;
````

## Members


`AutoInitialize`

For a subordinate DMA device, this member indicates whether to use the system DMA controller's autoinitialize mode. Set to <b>TRUE</b> to use autoinitialize mode. Otherwise, set this member to <b>FALSE</b>.

For a bus-master DMA device, the <b>AutoInitialize</b> value is not used.

`BusNumber`

The system-assigned bus number for the I/O bus. This member is not used by WDM drivers.

`DemandMode`

This member is used only if <b>Version</b> is DEVICE_DESCRIPTION_VERSION2.

For a subordinate DMA device, this member indicates whether to use the system DMA controller's demand mode. Set to <b>TRUE</b> to use demand mode. Otherwise, set this member to <b>FALSE</b>.

For a bus-master DMA device, the <b>DemandMode</b> value is not used.

If <b>Version</b> is DEVICE_DESCRIPTION_VERSION, DEVICE_DESCRIPTION_VERSION1, or DEVICE_DESCRIPTION_VERSION3, the <b>DemandMode</b> value is not used.

`DeviceAddress`

This member is used only if <b>Version</b> = DEVICE_DESCRIPTION_VERSION3.

For a subordinate DMA device, <b>DeviceAddress</b> is the memory-mapped address of the data register on the device that is used as the source or destination for a DMA transfer. This data register is located at a known, device-specific offset from the device start address. The width of this register is specified by the <b>DmaWidth</b> member. The device driver obtains the device start address from the resource list it receives in the <b>IRP_MN_START_DEVICE</b> request that starts the device. For more information about this address, see the description of the <b>u.Memory.Start</b> member in <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.

For a bus-master DMA device, the <b>DeviceAddress</b> member is not used.

`Dma32BitAddresses`

This member is used only if <b>Version</b> is DEVICE_DESCRIPTION_VERSION, DEVICE_DESCRIPTION_VERSION1, or DEVICE_DESCRIPTION_VERSION2.

<b>Dma32BitAddresses</b> specifies whether the device can use full 32-bit addresses for DMA operations. Set to <b>TRUE</b> if the device supports 32-bit addresses. Otherwise, set this member to <b>FALSE</b>.

If <b>Version</b> = DEVICE_DESCRIPTION_VERSION3, the <b>Dma32BitAddresses</b> value is not used.

`Dma64BitAddresses`

This member is used only if <b>Version</b> is DEVICE_DESCRIPTION_VERSION, DEVICE_DESCRIPTION_VERSION1, or DEVICE_DESCRIPTION_VERSION2.

<b>Dma64BitAddresses</b> specifies whether the device can use full 64-bit addresses for DMA operations. Set to <b>TRUE</b> if the device supports 64-bit addresses. Otherwise, set this member to <b>FALSE</b>.

If <b>Version</b> = DEVICE_DESCRIPTION_VERSION3, the <b>Dma64BitAddresses</b> value is not used.

`DmaAddressWidth`

This member is used only if <b>Version</b> = DEVICE_DESCRIPTION_VERSION3.

For a bus-master DMA device, <b>DmaAddressWidth</b> specifies the width, in bits, of a DMA address. The <b>DmaAddressWidth</b> value must be nonzero and must not exceed 64. If the memory address width is greater than the DMA address width, map registers are required to access a region of memory that is beyond the address reach of the DMA controller.

For a subordinate DMA device, the <b>DmaAddressWidth</b> value is not used. Instead, <b>IoGetDmaAdapter</b> assumes that the address width of a subordinate DMA device is the same as that of the underlying system DMA controller to which the device is connected.

`DmaChannel`

The number of the DMA channel to which a subordinate device is assigned. The device driver obtains this channel number from the resource list that it receives in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request that starts the device. For more information about this number, see the description of the <b>Dma.Channel</b> member in <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.

`DmaControllerInstance`

Not used.

`DmaPort`

The Microchannel-type bus port number. This parameter is obsolete, but is retained in the structure for compatibility with legacy drivers.

`DmaRequestLine`

This member is used only if <b>Version</b> = DEVICE_DESCRIPTION_VERSION3.

For a subordinate DMA device, <b>DmaRequestLine</b> specifies the request line on the DMA controller to which the device is connected. The device driver obtains the number of this request line from the resource list it receives in the <b>IRP_MN_START_DEVICE</b> request that starts the device. For more information about the request line number, see the description of the <b>u.DmaV3.RequestLine</b> member in <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.

For a bus-master DMA device, the <b>DmaRequestLine</b> value is not used.

`DmaSpeed`

This member is used only if <b>Version</b> is DEVICE_DESCRIPTION_VERSION, DEVICE_DESCRIPTION_VERSION1, or DEVICE_DESCRIPTION_VERSION2.

For a subordinate DMA device, this member specifies one of the following speeds for system DMA: <b>Compatible</b>, <b>TypeA</b>, <b>TypeB</b>, <b>TypeC</b>, or <b>TypeF</b>.

For a bus-master DMA device, the <b>DmaSpeed</b> value is not used.

If <b>Version</b> = DEVICE_DESCRIPTION_VERSION3, the <b>DmaSpeed</b> value is not used.

`DmaWidth`

For a subordinate DMA device, this member specifies the DMA data width for transfers by the system DMA controller. Possible values are <b>Width8Bits</b>, <b>Width16Bits</b>, <b>Width32Bits</b>, and <b>Width64Bits</b>.

For a bus-master DMA device, the <b>DmaWidth</b> value is not used.

`IgnoreCount`

Whether to ignore the DMA controller's transfer counter. Set to <b>TRUE</b> if the DMA controller in this platform does not maintain an accurate transfer counter, and therefore requires a workaround. Otherwise, set this member to <b>FALSE</b>.

If <b>Version</b> = DEVICE_DESCRIPTION_VERSION, the <b>IgnoreCount</b> value is not used.

For more information, see the Remarks section.

`InterfaceType`

The interface type of the I/O bus to use for DMA. Set this member to the <a href="..\wdm\ne-wdm-_interface_type.md">INTERFACE_TYPE</a> enumeration value that indicates the interface type. For more information, see the Remarks section.

`Master`

Whether the device is a bus-master DMA device. Set to <b>TRUE</b> if the device is a bus-master DMA device. Set to <b>FALSE</b> if it is a subordinate DMA device.

`MaximumLength`

The maximum number of bytes the device can transfer in a DMA operation that uses the allocated adapter object.

`Reserved1`

Reserved for system use. Must be <b>FALSE</b>.

`ScatterGather`

For a bus-master DMA device, this member indicates whether the device supports scatter/gather DMA. Set to <b>TRUE</b> if the device can do scatter/gather DMA. Otherwise, set this member to <b>FALSE</b>.

For a subordinate DMA device, the <b>ScatterGather</b> value is not used. Instead, <b>IoGetDmaAdapter</b> assumes that the scatter/gather capability of a subordinate DMA device is the same as that of the  underlying system DMA controller to which the device is connected.

`Version`

The version of this structure. The <b>Version</b> member of the <b>DEVICE_DESCRIPTION</b> structure that is passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine determines which version of the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure is returned by this routine. The following is a list of the possible values of the <b>Version</b> member and the corresponding <b>DMA_ADAPTER</b> versions:


#### DEVICE_DESCRIPTION_VERSION

If <b>Version</b> = <b>DEVICE_DESCRIPTION_VERSION</b>, <b>IoGetDmaAdapter</b> ignores the <b>IgnoreCount</b> member, and returns version 1 of the <b>DMA_ADAPTER</b> structure.


#### DEVICE_DESCRIPTION_VERSION1

If <b>Version</b> = <b>DEVICE_DESCRIPTION_VERSION1</b>, <b>IoGetDmaAdapter</b> uses the <b>IgnoreCount</b> member, and returns version 1 of the <b>DMA_ADAPTER</b> structure.


#### DEVICE_DESCRIPTION_VERSION2

If <b>Version</b> = <b>DEVICE_DESCRIPTION_VERSION2</b>, <b>IoGetDmaAdapter</b> uses the <b>IgnoreCount</b> member, and returns version 2 of the <b>DMA_ADAPTER</b> structure. Version 2 is available starting with  Windows XP.


#### DEVICE_DESCRIPTION_VERSION3

If <b>Version</b> = <b>DEVICE_DESCRIPTION_VERSION3</b>, <b>IoGetDmaAdapter</b> uses the <b>IgnoreCount</b> member, and returns version 3 of the <b>DMA_ADAPTER</b> structure. Version 3 is available starting with  Windows 8.

## Remarks
The driver of a device that uses DMA to transfer data uses the <b>DEVICE_DESCRIPTION</b> structure to pass information about the device to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine. The driver calls this routine to request an adapter object for a physical device object (PDO). This PDO represents the device's physical connection to the I/O bus to use for DMA. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546535">Getting an Adapter Object</a>.

To allocate resources for a DMA controller, the I/O manager needs information about the controller but can obtain some of this information only from a driver. For example, the driver for a bus-master device knows whether the device supports scatter/gather DMA or uses full 32-bit addresses. Or, the driver for a subordinate device can determine the DMA channel number from the resource list that the driver receives in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request that starts the device. The driver uses the <b>DEVICE_DESCRIPTION</b> structure to pass this information to the I/O manager.

Before calling <b>IoGetDmaAdapter</b>, the driver should first zero-initialize the entire <b>DEVICE_DESCRIPTION</b> structure, then fill in selected members to describe the device.

The <b>InterfaceType</b> member specifies the type of bus interface that will be used for DMA. If you set <b>InterfaceType</b> to <b>InterfaceTypeUndefined</b>, <b>IoGetDmaAdapter</b> queries the PDO to determine the correct interface type for your device. Or, you can specify an explicit interface type, such as <b>Internal</b>, <b>Isa</b>, <b>Eisa</b>, or <b>PCIBus</b>. For more information, see the list of supported interface types in <a href="..\wdm\ne-wdm-_interface_type.md">INTERFACE_TYPE</a>.

If the <b>ScatterGather</b> member is set to <b>TRUE</b> and the <b>InterfaceType</b> member is set to <b>PCIBus</b>, the <b>Dma32BitAddresses</b> member is ignored and <b>IoGetDmaAdapter</b> assumes that the device supports 32-bit DMA addresses.

If the <b>Dma64BitAddresses</b> member is set to <b>TRUE</b>, the <b>Dma32BitAddresses</b> member is ignored and <b>IoGetDmaAdapter</b> assumes that the device supports 64-bit DMA addresses.

To indicate that the DMA controller hardware cannot reliably maintain an accurate transfer count, set <b>IgnoreCount</b> to <b>TRUE</b>, and set <b>Version</b> to a value other than DEVICE_DESCRIPTION_VERSION. In a platform that has such a DMA controller, the operating system ignores the DMA transfer counter but must take special precautions to maintain data integrity during DMA operations. Typically, the use of a workaround to compensate for a deficient DMA controller degrades the speed of DMA transfers.

A driver should specify <b>TypeF</b> as the <b>DmaSpeed</b> value only if the computer's ACPI firmware supports it.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 2000. Supported starting with Windows 2000. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>

<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>

<a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>

<a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a>

<a href="..\wdm\ne-wdm-_interface_type.md">INTERFACE_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DEVICE_DESCRIPTION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>