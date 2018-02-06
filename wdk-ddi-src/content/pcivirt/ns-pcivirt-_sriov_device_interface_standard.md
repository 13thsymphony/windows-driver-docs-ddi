---
UID: NS:pcivirt._SRIOV_DEVICE_INTERFACE_STANDARD
title: "_SRIOV_DEVICE_INTERFACE_STANDARD"
author: windows-driver-content
description: Stores function pointers to callback functions implemented by the physical function (PF) driver in the device stack for the of the SR-IOV device.
old-location: pci\sriov_device_interface_standard.htm
old-project: PCI
ms.assetid: c71add7d-9920-4b2f-a46a-4a09a94f3900
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "*PSRIOV_DEVICE_INTERFACE_STANDARD, SRIOV_DEVICE_INTERFACE_STANDARD, PCI.sriov_device_interface_standard, pcivirt/SRIOV_DEVICE_INTERFACE_STANDARD, SRIOV_DEVICE_INTERFACE_STANDARD structure [Buses], _SRIOV_DEVICE_INTERFACE_STANDARD"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pcivirt.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Pcivirt.h
apiname:
-	SRIOV_DEVICE_INTERFACE_STANDARD
product: Windows
targetos: Windows
req.typenames: "*PSRIOV_DEVICE_INTERFACE_STANDARD, SRIOV_DEVICE_INTERFACE_STANDARD"
---

# _SRIOV_DEVICE_INTERFACE_STANDARD structure
Stores function pointers to callback functions implemented by the physical function (PF) driver  in the device stack for the of the SR-IOV device.

## Syntax
````
typedef struct _SRIOV_DEVICE_INTERFACE_STANDARD {
  USHORT                           Size;
  USHORT                           Version;
  PVOID                            Context;
  PINTERFACE_REFERENCE             InterfaceReference;
  PINTERFACE_REFERENCE             InterfaceDereference;
  PSRIOV_READ_CONFIG               ReadVfConfig;
  PSRIOV_WRITE_CONFIG              WriteVfConfig;
  PSRIOV_READ_BLOCK                ReadVfConfigBlock;
  PSRIOV_WRITE_BLOCK               WriteVfConfigBlock;
  PSRIOV_QUERY_PROBED_BARS         QueryProbedBars;
  PSRIOV_GET_VENDOR_AND_DEVICE_IDS GetVendorAndDevice;
  PSRIOV_GET_DEVICE_LOCATION       GetDeviceLocation;
  PSRIOV_RESET_FUNCTION            ResetVf;
  PSRIOV_SET_POWER_STATE           SetVfPowerState;
  PSRIOV_GET_RESOURCE_FOR_BAR      GetResourceForBar;
  PSRIOV_QUERY_LUID                QueryLuid;
} SRIOV_DEVICE_INTERFACE_STANDARD, SRIOV_DEVICE_INTERFACE_STANDARD;
````

## Members


`Context`

Driver-defined context passed by the driver.

`GetDeviceLocation`

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/705b52e3-f695-4c58-9ae2-5a806f1e2140">SRIOV_GET_DEVICE_LOCATION</a> callback function that allows the a non-privileged VM to determine the bus to which the device is attached.

`GetResourceForBar`

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/b52bafee-d541-4396-be0a-06956d07fb2b">SRIOV_GET_RESOURCE_FOR_BAR</a> callback function that gets the translated resource for a specific BAR.

`GetVendorAndDevice`

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/d08bbaea-6f2b-49ef-bb8b-c1fe357e1c90">SRIOV_GET_VENDOR_AND_DEVICE_IDS</a> callback function that supplies the values from which the Plug and Play IDs for device is derived.

`InterfaceDereference`

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="..\wdm\nc-wdm-pinterface_dereference.md">InterfaceDereference</a>.

`InterfaceReference`

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="..\wdm\nc-wdm-pinterface_reference.md">InterfaceReference</a>.

`QueryLuid`

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/9bb8e54f-b42a-4f61-a3f5-6972141c8f28">SRIOV_QUERY_LUID</a> callback function that gets the unique identifier of the VF.

`QueryProbedBars`

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/422a9212-7227-4508-8f06-0056349fa835">SRIOV_QUERY_PROBED_BARS</a> callback function that allows a non-privileged VM to determine the value of the VF’s Base Address Registers if the value of -1 previously is written.

`ReadVfConfig`

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/0fef9d53-b8af-4c9b-9914-982bcfc26517">SRIOV_READ_CONFIG</a> callback function that serves as a handler for reading the VF’s configurations space from the non-privileged VM.

`ReadVfConfigBlock`

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/af0d3465-2854-47d9-a6a4-06f510229a59">SRIOV_READ_BLOCK</a> callback function that serves as a handler for reading blocks of configuration data from the non-privileged VM.

`ResetVf`

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/30c01528-8254-431f-aaba-79c05f66fc00">SRIOV_RESET_FUNCTION</a> callback function that causes the VF to be reset.

`SetVfPowerState`

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/d43a21cb-5cee-4e72-8f0c-7aa8b2453507">SRIOV_SET_POWER_STATE</a> callback function that serves as a handle for changing the device’s power state from the non-privileged VM.

`Size`

Size of this structure.

`Version`

Version of this structure

`WriteVfConfig`

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/323c8150-ef58-42a4-8c8b-77081ecb64b3">SRIOV_WRITE_CONFIG</a> callback function that serves as a handler for writing the VF’s configuration space from the non-privileged VM.

`WriteVfConfigBlock`

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/da47d601-2fab-49bb-b669-909a2e5c95c0">SRIOV_WRITE_BLOCK</a> callback function that serves as a handler for writing blocks of configuration data from the non-privileged VM..


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pcivirt.h |

## See Also

<a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>

<a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdf_query_interface_config_init.md">WDF_QUERY_INTERFACE_CONFIG_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20SRIOV_DEVICE_INTERFACE_STANDARD structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>