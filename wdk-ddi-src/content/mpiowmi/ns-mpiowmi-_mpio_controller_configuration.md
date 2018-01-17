---
UID: NS:mpiowmi._MPIO_CONTROLLER_CONFIGURATION
title: _MPIO_CONTROLLER_CONFIGURATION
author: windows-driver-content
description: The MPIO_CONTROLLER_CONFIGURATION structure provides a top-level view of the storage controllers and the targets that are connected to them in the system.
old-location: storage\mpio_controller_configuration.htm
old-project: storage
ms.assetid: af608197-fa2b-474f-aa87-eb933a57b8cc
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MPIO_CONTROLLER_CONFIGURATION, *PMPIO_CONTROLLER_CONFIGURATION, MPIO_CONTROLLER_CONFIGURATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MPIO_CONTROLLER_CONFIGURATION
req.alt-loc: mpiowmi.h
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
req.typenames: *PMPIO_CONTROLLER_CONFIGURATION, MPIO_CONTROLLER_CONFIGURATION
---

# _MPIO_CONTROLLER_CONFIGURATION structure



## -description
The MPIO_CONTROLLER_CONFIGURATION structure provides a top-level view of the storage controllers and the targets that are connected to them in the system.



## -syntax

````
typedef struct _MPIO_CONTROLLER_CONFIGURATION {
  ULONG                NumberControllers;
  MPIO_CONTROLLER_INFO ControllerInfo[1];
} MPIO_CONTROLLER_CONFIGURATION, *PMPIO_CONTROLLER_CONFIGURATION;
````


## -struct-fields

### -field NumberControllers

An unsigned 32-bitfield that represents the total number of controllers on the system that are known to MPIO.


### -field ControllerInfo

An array with information about all the controllers and all targets in the system. The number of elements of the array is given by <i>NumberControllers</i> and each element of the array is an instance of an MPIO_CONTROLLER_INFO structure.


## -remarks
