---
UID : NS:mpiowmi._MPIOMoveDevice_IN
title : "_MPIOMoveDevice_IN"
author : windows-driver-content
description : The MPIOMoveDevice_IN structure is used to set the active path on the device.
old-location : storage\mpiomovedevice_in.htm
old-project : storage
ms.assetid : 2652874f-70d0-4eff-a46d-778a68d55cab
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : structs-scsibus_d1c11b7d-5c45-441b-8362-642db610e19e.xml, PMPIOMoveDevice_IN structure pointer [Storage Devices], storage.mpiomovedevice_in, _MPIOMoveDevice_IN, MPIOMoveDevice_IN structure [Storage Devices], mpiowmi/MPIOMoveDevice_IN, MPIOMoveDevice_IN, *PMPIOMoveDevice_IN, PMPIOMoveDevice_IN, mpiowmi/PMPIOMoveDevice_IN
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
req.typenames : MPIOMoveDevice_IN, *PMPIOMoveDevice_IN
---

# _MPIOMoveDevice_IN structure
The MPIOMoveDevice_IN structure is used to set the active path on the device.

## Syntax
````
typedef struct _MPIOMoveDevice_IN {
  ULONG     DiskOrdinal;
  ULONG     Flags;
  ULONGLONG PathID;
} MPIOMoveDevice_IN, *PMPIOMoveDevice_IN;
````

## Members


`DiskOrdinal`

A 32-bitfield that specifies the MPIO disk ordinal value.

`Flags`

A 32-bitfield that specifies the flags that are associated with the device move operation.

`PathID`

A 64-bitfield that specifies the path that is associated with the device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mpiowmi.h (include Mpiowmi.h) |