---
UID: NF.srb.ScsiPortSetBusDataByOffset
title: ScsiPortSetBusDataByOffset function
author: windows-driver-content
description: The ScsiPortSetBusDataByOffset routine sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface.
old-location: storage\scsiportsetbusdatabyoffset.htm
old-project: storage
ms.assetid: 64f46049-fbf0-4d9b-b5fe-9877a964755f
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ScsiPortSetBusDataByOffset
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
req.alt-api: ScsiPortSetBusDataByOffset
req.alt-loc: Scsiport.lib,Scsiport.dll
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
req.product: Windows 10 or later.
---

# ScsiPortSetBusDataByOffset function



## -description
The <b>ScsiPortSetBusDataByOffset</b> routine sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface. 


## -syntax

````
ULONG ScsiPortSetBusDataByOffset(
  _In_ PVOID DeviceExtension,
  _In_ ULONG BusDataType,
  _In_ ULONG SystemIoBusNumber,
  _In_ ULONG SlotNumber,
  _In_ PVOID Buffer,
  _In_ ULONG Offset,
  _In_ ULONG Length
);
````


## -parameters

### -param DeviceExtension [in]

Pointer to the miniport driver's device extension. 

### -param BusDataType [in]

Contains a value of type <a href="kernel.bus_data_type">BUS_DATA_TYPE</a> that specifies the type of bus data to be set. Currently, its value can be <b>PCIConfiguration</b>. However, additional types of standardized, dynamically configurable buses will be supported in future. The upper bound on the bus types supported is always <b>MaximumBusDataType</b>. 

### -param SystemIoBusNumber [in]

Specifies the system-assigned number of the I/O bus on which the HBA is connected. The miniport driver's <a href="storage.hwscsifindadapter">HwScsiFindAdapter</a> routine obtains this value from the input PORT_CONFIGURATION_INFORMATION <b>SystemIoBusNumber</b> member. 

### -param SlotNumber [in]

Specifies the logical slot number of the HBA.
When <b>PCIConfiguration</b> is specified as the <i>BusDataType</i>, this parameter must be specified as a PCI_SLOT_NUMBER-type value. 

### -param Buffer [in]

Pointer to a caller-supplied storage area with configuration information specific to <i>BusDataType</i>. 
When <b>PCIConfiguration</b> is specified, the buffer contains some or all of the PCI_COMMON_CONFIG information for the given <i>SlotNumber</i>. The specified <i>Offset</i> and <i>Length</i> determine how much information is supplied. 

### -param Offset [in]

Specifies the byte offset within the PCI_COMMON_CONFIG structure at which the caller-supplied configuration values begin. A miniport driver can use PCI_COMMON_HDR_LENGTH to specify the offset of the device-specific area in PCI_COMMON_CONFIG. 

### -param Length [in]

Specifies the number of bytes in the storage area at <i>Buffer</i>. 

## -returns
<b>ScsiPortSetBusDataByOffset</b> returns the number of bytes of data successfully set for the given <i>SlotNumber</i>. If the given <i>BusDataType</i> is not valid for the current platform or if the supplied information is invalid, <b>ScsiPortSetBusDataByOffset</b> returns zero. 

## -remarks
Miniport drivers of HBAs on a PCI bus seldom call <b>ScsiPortSetBusDataByOffset</b> unless unusual circumstances or the nature of a particular driver's HBA requires such a call. For example, a miniport driver might call <b>ScsiPortSetBusDataByOffset</b> to clear a bit in the PCI status register if its HBA signals a target abort during initialization or to set device-specific configuration data for the HBA.

<b>ScsiPortSetBusDataByOffset</b> can be called only from the miniport driver's <i>HwScsiFindAdapter</i> routine or from HwScsiAdapterControl when the control type is <b>ScsiSetRunningConfig</b>. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Srb.h (include Miniport.h or Scsi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Scsiport.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546633">HalSetBusDataByOffset</a>
</dt>
<dt>
<a href="storage.hwscsifindadapter">HwScsiFindAdapter</a>
</dt>
<dt>
<a href="kernel.pci_common_config">PCI_COMMON_CONFIG</a>
</dt>
<dt>
<a href="kernel.pci_slot_number">PCI_SLOT_NUMBER</a>
</dt>
<dt>
<a href="storage.port_configuration_information__scsi_">PORT_CONFIGURATION_INFORMATION (SCSI)</a>
</dt>
<dt>
<a href="storage.scsiportgetbusdata">ScsiPortGetBusData</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortSetBusDataByOffset routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
