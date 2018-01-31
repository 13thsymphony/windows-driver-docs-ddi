---
UID : NC:wdm.SET_VIRTUAL_DEVICE_DATA
title : SET_VIRTUAL_DEVICE_DATA
author : windows-driver-content
description : The SetVirtualFunctionData routine writes data to the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.
old-location : pci\setvirtualfunctiondata.htm
old-project : PCI
ms.assetid : 12CC6973-E691-425E-A8E8-839F83116D29
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : PCI.setvirtualfunctiondata, SetVirtualFunctionData routine, SetVirtualFunctionData, SET_VIRTUAL_DEVICE_DATA, SET_VIRTUAL_DEVICE_DATA, wdm/SetVirtualFunctionData
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Desktop
req.target-min-winverclnt : Supported in Windows Server 2012 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= APC_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME"
req.product : Windows 10 or later.
---


# SET_VIRTUAL_DEVICE_DATA function
The  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451552">SetVirtualFunctionData</a> routine writes data to the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.

## Syntax

```
SET_VIRTUAL_DEVICE_DATA SetVirtualDeviceData;

ULONG SetVirtualDeviceData(
  PVOID Context,
  USHORT VirtualFunction,
  PVOID Buffer,
  ULONG Offset,
  ULONG Length
)
{...}
```

## Parameters

`Context`

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.

`VirtualFunction`

A zero-based value that specifies the VF on the device from which data is to be written.

`Buffer`

A pointer to the buffer that contains the configuration information to be written to the PCIe configuration space of the VF.

`Offset`

The offset into the PCIe configuration space data of the VF. This member specifies where this write operation begins.

`Length`

The length, in bytes, of the data to be written.


## Return Value

The 
      <a href="https://msdn.microsoft.com/library/windows/hardware/hh451552">SetVirtualFunctionData</a> routine returns the length, in bytes, of the PCIe configuration data that was written after a successful write operation. If the write operation is unsuccessful, the routine returns zero.

## Remarks

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451552">SetVirtualFunctionData</a> routine is similar to the <a href="..\wdm\nc-wdm-get_set_device_data.md">SetBusData</a> routine, except that it writes PCIe configuration data to a VF instead of to a device's physical function (PF).

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451552">SetVirtualFunctionData</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface. The <a href="..\wdm\nc-wdm-get_set_device_data.md">SetBusData</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546561">GUID_BUS_INTERFACE_STANDARD</a> interface.
<div class="alert"><b>Note</b>  The virtualization stack calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh451552">SetVirtualFunctionData</a> when a driver that is running in the guest operating system calls the <a href="..\wdm\nc-wdm-get_set_device_data.md">SetBusData</a> routine.</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h) |
| **Library** |  |
| **IRQL** | "<= APC_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nc-wdm-get_set_device_data.md">SetBusData</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\pci]:%20SET_VIRTUAL_DEVICE_DATA routine%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>