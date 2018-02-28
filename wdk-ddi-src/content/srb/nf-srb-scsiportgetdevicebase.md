---
UID: NF:srb.ScsiPortGetDeviceBase
title: ScsiPortGetDeviceBase function
author: windows-driver-content
description: The ScsiPortGetDeviceBase routine returns a mapped, logical base address that can be used to communicate with an HBA.
old-location: storage\scsiportgetdevicebase.htm
old-project: storage
ms.assetid: d8d14818-4b84-4c65-a29e-2cd97e8bfbe9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ScsiPortGetDeviceBase, ScsiPortGetDeviceBase routine [Storage Devices], scsiprt_2924bfb1-e5a0-4533-afd7-65d2d7962b46.xml, srb/ScsiPortGetDeviceBase, storage.scsiportgetdevicebase
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Scsiport.lib
-	Scsiport.dll
api_name:
-	ScsiPortGetDeviceBase
product: Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---


# ScsiPortGetDeviceBase function
The <b>ScsiPortGetDeviceBase</b> routine returns a mapped, logical base address that can be used to communicate with an HBA. Every miniport driver must pass mapped, logical access range addresses to the <b>ScsiPort..Port</b><i>Xxx</i> and <b>ScsiPort..Register</b><i>Xxx</i> routines to communicate with its HBA(s).
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
PVOID ScsiPortGetDeviceBase(
  _In_ PVOID                 HwDeviceExtension,
  _In_ INTERFACE_TYPE        BusType,
  _In_ ULONG                 SystemIoBusNumber,
  _In_ SCSI_PHYSICAL_ADDRESS IoAddress,
  _In_ ULONG                 NumberOfBytes,
  _In_ BOOLEAN               InIoSpace
);
````

## Parameters

`HwDeviceExtension`

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device.

`BusType`

Specifies the interface type of the I/O bus on which the HBA is connected. The miniport driver's <a href="..\srb\nc-srb-phw_find_adapter.md">HwScsiFindAdapter</a> routine obtains the value for this parameter from the <b>AdapterInterfaceType</b> member of the input PORT_CONFIGURATION_INFORMATION.

`SystemIoBusNumber`

Specifies the system-assigned number of the I/O bus on which the HBA is connected. The <i>HwScsiFindAdapter</i> routine obtains the value for this parameter from the <b>SystemIoBusNumber</b> member of the input PORT_CONFIGURATION_INFORMATION.

`IoAddress`

Specifies the bus-relative base address of a range used by the HBA. The <i>HwScsiFindAdapter</i> routine obtains the value for this parameter from one of the <b>AccessRanges</b> elements in the PORT_CONFIGURATION_INFORMATION if the port driver supplies range-configuration information. Otherwise, this address can be a value returned by <b>ScsiPortGetBusData</b> or a miniport driver-supplied default value. Avoid using a base address of zero because its successful return status can conflict with the error status (<b>NULL</b>).

`NumberOfBytes`

Specifies the size in bytes of the range that the mapping should cover. The <i>HwScsiFindAdapter</i> routine obtains the value of this parameter from the same <b>AccessRanges</b> element as <i>IoAddress</i> if the port driver supplies range configuration information. Otherwise, this value can be returned by <b>ScsiPortGetBusData</b> or a miniport driver-supplied default. In any case, the driver must not access the hardware outside of the returned, mapped range.

`InIoSpace`

<b>TRUE</b> indicates the range to be mapped is in I/O space, and the miniport driver will pass mapped addresses in this range to the <b>ScsiPort...Port</b><i>Xxx</i> to communicate with the HBA. The <i>HwScsiFindAdapter</i> routine obtains the value of this parameter from the same <b>AccessRanges</b> element as <i>IoAddress</i>. Note that a miniport driver <i>must invert</i> the value of the <b>InMemorySpace</b> member in an ACCESS_RANGE-type element before it is passed to <b>ScsiPortGetDeviceBase</b> as the <i>InIoSpace</i> argument. <b>FALSE</b> indicates that the range to be mapped is in memory space.


## Return Value

<b>ScsiPortGetDeviceBase</b> returns a mapped logical base address for the given <i>IoAddress</i> if it successfully mapped the given range from <i>IoAddress</i> to <i>NumberOfBytes</i>. If a given range cannot be mapped, <b>ScsiPortGetDeviceBase</b> returns <b>NULL</b>.

## Remarks

NT-based operating system platforms can have several types of I/O buses and several I/O buses of the same type. Moreover, the HAL can map I/O space to memory in some platforms.

Consequently, a miniport driver cannot use bus-relative access range addresses to communicate with its HBA. To maintain miniport driver portability across CISC- and RISC-based machines, the addresses they use to access HBAs must be translated with <b>ScsiPortGetDeviceBase</b>.

Every miniport driver must use system-space logical range addresses, mapped by <b>ScsiPortGetDeviceBase</b>, to communicate with its HBA(s). Calls to the <b>ScsiPort...Port/Register</b><i>Xxx</i> routines require these mapped, logical addresses.

<b>ScsiPortGetDeviceBase</b> can be called several times, depending on how many HBAs the miniport driver supports and how many access ranges each HBA requires. Each mapped range corresponds to a range of bus-relative device addresses specified in an ACCESS_RANGE-type element of the <b>AccessRanges</b> array.

<b>ScsiPortGetDeviceBase</b> can be called only from a miniport driver's <a href="..\srb\nc-srb-phw_find_adapter.md">HwScsiFindAdapter</a> routine or from HwScsiAdapterControl when the control type is <b>ScsiSetRunningConfig</b>. Calls from other miniport driver  routines will result in system failure or in incorrect operation for the caller.

Follow these guidelines for calling <b>ScsiPortGetDeviceBase</b>:

<ul>
<li>
If <i>HwScsiFindAdapter</i> is using a miniport driver-supplied set of default bus-relative access ranges or values returned by <b>ScsiPortGetBusData</b>, it should call <a href="..\srb\nf-srb-scsiportvalidaterange.md">ScsiPortValidateRange</a> before attempting to call <b>ScsiPortGetDeviceBase</b>.

</li>
<li>
If <i>HwScsiFindAdapter</i> determines that a particular HBA is not one that the miniport driver supports, it must call <b>ScsiPortFreeDeviceBase</b> to release the mapping(s) it set up to communicate with that HBA.

</li>
</ul>
The logical address returned by <b>ScsiPortGetDeviceBase</b> should be used for all subsequent references made to the hardware but should <i>not</i> be added to any <b>AccessRanges</b> specification in the PORT_CONFIGURATION_INFORMATION. Miniport driver writers should make no assumptions about how many bits are used in the logical base address returned by <b>ScsiPortGetDeviceBase</b>.

<b>ScsiPortGetDeviceBase</b> uses <b>SCSI_PHYSICAL_ADDRESS</b> to represent bus-relative addresses.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef PHYSICAL_ADDRESS SCSI_PHYSICAL_ADDRESS, *PSCSI_PHYSICAL_ADDRESS;
</pre>
</td>
</tr>
</table></span></div>
The <b>SCSI_PHYSICAL_ADDRESS</b> type is an operating system-independent data type that SCSI miniport drivers use to represent either a physical addresses or a bus-relative address. 

<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h (include Miniport.h, Scsi.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="..\srb\nf-srb-scsiportgetbusdata.md">ScsiPortGetBusData</a>



<a href="..\strmini\ns-strmini-_access_range.md">ACCESS_RANGE</a>



<a href="..\srb\nf-srb-scsiportvalidaterange.md">ScsiPortValidateRange</a>



<a href="..\srb\nf-srb-scsiportfreedevicebase.md">ScsiPortFreeDeviceBase</a>



<a href="..\srb\nc-srb-phw_find_adapter.md">HwScsiFindAdapter</a>



<a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION (SCSI)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortGetDeviceBase routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>