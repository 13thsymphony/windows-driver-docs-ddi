---
UID: NF:ucxcontroller.UCX_CONTROLLER_CONFIG_SET_PCI_INFO
title: UCX_CONTROLLER_CONFIG_SET_PCI_INFO function
author: windows-driver-content
description: Initializes a UCX_CONTROLLER_CONFIG structure with the specified values for the controller with PCI as the parent bus type.
old-location: buses\_ucx_controller_config_set_pci_info.htm
old-project: usbref
ms.assetid: 493B8E5B-D2CC-453E-8202-69337FAC85ED
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UCX_CONTROLLER_CONFIG_SET_PCI_INFO, UCX_CONTROLLER_CONFIG_SET_PCI_INFO function [Buses], buses._ucx_controller_config_set_pci_info, ucxcontroller/UCX_CONTROLLER_CONFIG_SET_PCI_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucxcontroller.h
api_name:
-	UCX_CONTROLLER_CONFIG_SET_PCI_INFO
product:
- Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_STATE
req.product: Windows 10 or later.
---


# UCX_CONTROLLER_CONFIG_SET_PCI_INFO function
Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt188057">UCX_CONTROLLER_CONFIG</a> structure with the specified values for the controller with PCI as the parent bus type.

## Syntax

```
void UCX_CONTROLLER_CONFIG_SET_PCI_INFO(
  PUCX_CONTROLLER_CONFIG Config,
  ULONG                  VendorId,
  ULONG                  DeviceId,
  USHORT                 RevisionId,
  ULONG                  BusNumber,
  ULONG                  DeviceNumber,
  ULONG                  FunctionNumber
);
```

## Parameters

`Config`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt188057">UCX_CONTROLLER_CONFIG</a> structure to initialize.

`VendorId`

Specifies the vendor identifier for the device as assigned by the PCI SIG.

`DeviceId`

Specifies the device identifier assigned by the manufacturer.

`RevisionId`

Specifies the revision level of the device described by the <b>DeviceID</b> member.

`BusNumber`

Specifies the bus number that identifies the bus instance that a device instance is attached to.

`DeviceNumber`

Specifies the device number that is assigned to the logical PCI slot.

`FunctionNumber`

Specifies the specific function on the device that is located in the logical PCI slot.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10  |
| **Target Platform** | Windows |
| **Header** | ucxcontroller.h (include Ucxclass.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188057">UCX_CONTROLLER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>