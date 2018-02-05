---
UID : NS:mpiowmi._MPIO_CONTROLLER_INFO
title : "_MPIO_CONTROLLER_INFO"
author : windows-driver-content
description : The MPIO_CONTROLLER_INFO structure represents a storage controller.
old-location : storage\mpio_controller_info.htm
old-project : storage
ms.assetid : 30600e86-dd35-4498-91a8-14a722b2e868
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : MPIO_CONTROLLER_INFO structure [Storage Devices], mpiowmi/MPIO_CONTROLLER_INFO, storage.mpio_controller_info, mpiowmi/PMPIO_CONTROLLER_INFO, PMPIO_CONTROLLER_INFO, MPIO_CONTROLLER_INFO, *PMPIO_CONTROLLER_INFO, _MPIO_CONTROLLER_INFO, PMPIO_CONTROLLER_INFO structure pointer [Storage Devices], structs-scsibus_6b7edecb-9938-49fb-8367-5d176f83c0a5.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : mpiowmi.h
req.include-header : Mpiowmi.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : MPIO_CONTROLLER_INFO, *PMPIO_CONTROLLER_INFO
---

# _MPIO_CONTROLLER_INFO structure
The MPIO_CONTROLLER_INFO structure represents a storage controller.

## Syntax
````
typedef struct _MPIO_CONTROLLER_INFO {
  ULONG IdentifierType;
  ULONG IdentifierLength;
  UCHAR Identifier[32];
  ULONG ControllerState;
  ULONG Pad;
  WCHAR AssociatedDsm[63 + 1];
} MPIO_CONTROLLER_INFO, *PMPIO_CONTROLLER_INFO;
````

## Members


`AssociatedDsm`

A string field of maximum length 63 characters. This string field returns the friendly name of the DSM that controls the devices that are exposed by this controller.

`ControllerState`

An unsigned 32-bitfield that represents the controller state.

`Identifier`

A 32-byte array that contains the actual identifier (serial number) of the controller.

`IdentifierLength`

An unsigned 32-bitfield that represents the length of the controller's identifier.

`IdentifierType`

An unsigned 32-bitfield that represents the identifier type for the controller.

`Pad`

Should be zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mpiowmi.h (include Mpiowmi.h) |