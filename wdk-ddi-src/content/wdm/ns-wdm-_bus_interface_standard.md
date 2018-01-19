---
UID : NS:wdm._BUS_INTERFACE_STANDARD
title : _BUS_INTERFACE_STANDARD
author : windows-driver-content
description : The BUS_INTERFACE_STANDARD interface structure enables device drivers to make direct calls to parent bus driver routines. This structure defines the GUID_BUS_INTERFACE_STANDARD interface.
old-location : kernel\bus_interface_standard.htm
old-project : kernel
ms.assetid : cebe5b45-2a7a-4e33-aacb-5cc3ee112808
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _BUS_INTERFACE_STANDARD, BUS_INTERFACE_STANDARD, *PBUS_INTERFACE_STANDARD
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BUS_INTERFACE_STANDARD
req.alt-loc : Wdm.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL (see Remarks section)
req.typenames : BUS_INTERFACE_STANDARD, *PBUS_INTERFACE_STANDARD
req.product : Windows 10 or later.
---

# _BUS_INTERFACE_STANDARD structure
The <b>BUS_INTERFACE_STANDARD</b> interface structure enables device drivers to make direct calls to parent bus driver routines. This structure defines the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546561">GUID_BUS_INTERFACE_STANDARD</a> interface.

## Syntax
````
typedef struct _BUS_INTERFACE_STANDARD {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  PTRANSLATE_BUS_ADDRESS TranslateBusAddress;
  PGET_DMA_ADAPTER       GetDmaAdapter;
  PGET_SET_DEVICE_DATA   SetBusData;
  PGET_SET_DEVICE_DATA   GetBusData;
} BUS_INTERFACE_STANDARD, *PBUS_INTERFACE_STANDARD;
````

## Members

        
            `Context`

            A pointer to interface-specific context information.
        
            `GetBusData`

            A pointer to a <a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a> routine that reads data from the device's configuration space.
        
            `GetDmaAdapter`

            A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/gg604851">GetDmaAdapter</a> routine that returns a DMA adapter structure (<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>) for the target device.
        
            `InterfaceDereference`

            A pointer to an <a href="..\wdm\nc-wdm-pinterface_dereference.md">InterfaceDereference</a> routine that decrements the interface's reference count.
        
            `InterfaceReference`

            A pointer to an <a href="..\wdm\nc-wdm-pinterface_reference.md">InterfaceReference</a> routine that increments the interface's reference count.
        
            `SetBusData`

            A pointer to a <a href="..\wdm\nc-wdm-get_set_device_data.md">SetBusData</a> routine that writes data to the device's configuration space.
        
            `Size`

            The size, in bytes, of this structure.
        
            `TranslateBusAddress`

            A pointer to a <a href="..\wdm\nc-wdm-translate_bus_address.md">TranslateBusAddress</a> routine that translates addresses on the parent bus to logical addresses.
        
            `Version`

            The driver-defined interface version.

    ## Remarks
        The <b>BUS_INTERFACE_STANDARD</b> structure is an extension of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure.

Some operations on a device are reserved for the device's parent bus driver. These operations might include accessing the device-specific configuration space of a bus or programming a DMA controller.

To read from or write to a device's configuration space, a device driver must rely on the agency of the bus driver in either of two ways:

By sending the I/O request packets (IRPs) <a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff551769">IRP_MN_WRITE_CONFIG</a> to the bus driver.

By obtaining an interface from the bus driver. The device driver can then access its device's configuration space by making direct calls to the bus driver routines provided by the <b>BUS_INTERFACE_STANDARD</b> interface structure. Its member routines, <a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a> and <a href="..\wdm\nc-wdm-get_set_device_data.md">SetBusData</a>, can be used to read from and write to a device's configuration space, respectively.



For more information about the ways to access configuration space, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540450">Accessing Device Configuration Space</a>.

Some types of devices, such as a bus-mastering storage device, have on-board DMA controllers. However, the device drivers for these devices cannot program these DMA controllers directly. Instead they must rely on routines provided by the parent bus driver. For a device driver to program the DMA controller for its device, it must first request an adapter object from the parent bus driver. The adapter object contains the routines supplied by the bus driver that can be used to program the device's DMA controller. Device drivers must rely on the <b>BUS_INTERFACE_STANDARD</b>, either directly or indirectly, to obtain the adapter object.

If the driver is executing at IRQL = PASSIVE_LEVEL, it should obtain a device's DMA adapter object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>. <b>IoGetDmaAdapter</b> detects whether the bus driver supports the <b>BUS_INTERFACE_STANDARD</b> interface.   If it does, <b>IoGetDmaAdapter</b> calls the routine pointed to by the <a href="https://msdn.microsoft.com/library/windows/hardware/gg604851">GetDmaAdapter</a> member of this interface to obtain the adapter object. Otherwise, <b>IoGetDmaAdapter</b> calls an equivalent legacy routine.

However, if a driver must obtain an adapter object while running at IRQL &gt;= DISPATCH_LEVEL, it cannot do so with <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>. In this case, the driver must query for the <b>BUS_INTERFACE_STANDARD</b> interface while still at IRQL = PASSIVE_LEVEL by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

    ## See Also

        <dl>
<dt>
<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/gg604850">GetBusData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/gg604851">GetDmaAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546561">GUID_BUS_INTERFACE_STANDARD</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pinterface_dereference.md">InterfaceDereference</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pinterface_reference.md">InterfaceReference</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/d57c30b8-83bd-41c9-906d-b8c95f8ca54e">IRP_MN_WRITE_CONFIG </a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-get_set_device_data.md">SetBusData</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-translate_bus_address.md">TranslateBusAddress</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BUS_INTERFACE_STANDARD structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>