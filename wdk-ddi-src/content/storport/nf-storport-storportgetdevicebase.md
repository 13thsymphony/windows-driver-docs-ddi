---
UID: NF:storport.StorPortGetDeviceBase
title: StorPortGetDeviceBase function
author: windows-driver-content
description: The StorPortGetDeviceBase routine maps an I/O address to system address space.
old-location: storage\storportgetdevicebase.htm
old-project: storage
ms.assetid: 6d25f2fb-be77-480f-b07c-294ab8a4272e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortGetDeviceBase, storprt_8be3e3d9-dae5-49cb-aa44-31d3be745045.xml, storport/StorPortGetDeviceBase, storage.storportgetdevicebase, StorPortGetDeviceBase routine [Storage Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortGetDeviceBase
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortGetDeviceBase function
The <b>StorPortGetDeviceBase</b> routine maps an I/O address to system address space.

## Syntax

````
STORPORT_API PVOID StorPortGetDeviceBase(
  _In_ PVOID                 HwDeviceExtension,
  _In_ INTERFACE_TYPE        BusType,
  _In_ ULONG                 SystemIoBusNumber,
  _In_ STOR_PHYSICAL_ADDRESS IoAddress,
  _In_ ULONG                 NumberOfBytes,
  _In_ BOOLEAN               InIoSpace
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

`BusType`

Specifies the interface type of the I/O bus on which the HBA is connected. The miniport driver's <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine obtains the value for this parameter from the <b>AdapterInterfaceType</b> member of the input <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>.

`SystemIoBusNumber`

Specifies the system-assigned number of the I/O bus on which the HBA is connected. The <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine obtains the value for this parameter from the <b>SystemIoBusNumber</b> member of the input <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>.

`IoAddress`

Specifies the bus-relative base address of a range used by the HBA. The <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine obtains the value for this parameter from one of the <b>AccessRanges</b> elements in the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> if the port driver supplies range-configuration information. Otherwise, this address can be a value returned by <a href="..\storport\nf-storport-storportgetbusdata.md">StorPortGetBusData</a> or a miniport driver-supplied default value. Avoid using a base address of zero because its successful return status can conflict with the error status (<b>NULL</b>).

`NumberOfBytes`

Specifies the size in bytes of the range that the mapping should cover. The <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine obtains the value of this parameter from the same <b>AccessRanges</b> element as <i>IoAddress</i> if the port driver supplies range configuration information. Otherwise, this value can be returned by <a href="..\storport\nf-storport-storportgetbusdata.md">StorPortGetBusData</a> or a miniport driver-supplied default. In any case, the driver must not access the hardware outside of the returned, mapped range.

`InIoSpace`

TRUE indicates the range to be mapped is in I/O space, and the miniport driver will pass mapped addresses in this range to the Storport <i>port</i> read/write routines to communicate with the HBA. The <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine obtains the value of this parameter from the same <b>AccessRanges</b> element as <i>IoAddress</i>. Note that a miniport driver <i>must invert</i> the value of the <b>InMemorySpace</b> member in an ACCESS_RANGE-type element before it is passed to <b>StorPortGetDeviceBase</b> as the <i>InIoSpace</i> argument. <b>FALSE</b> indicates that the range to be mapped is in memory space.


## Return Value

A mapped, logical base address corresponding to the bus-relative address supplied in the <i>IoAddress</i> parameter.

## Remarks

Every miniport driver must pass mapped, logical access range addresses to the Storport <i>port</i> read/write routines and the Storport <i>register</i> read/write routines when communicating with its HBA(s).

This routine supports only those addresses that were assigned to the driver by the system Plug and Play (PnP) manager.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\storport\nf-storport-storportfreedevicebase.md">StorPortFreeDeviceBase</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetDeviceBase routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>