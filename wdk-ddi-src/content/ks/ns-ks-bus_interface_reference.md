---
UID : NS:ks.BUS_INTERFACE_REFERENCE
title : BUS_INTERFACE_REFERENCE
author : windows-driver-content
description : A software device enumerator exports this interface to allow drivers to reference count physical device objects (PDOs) such that the device remains active while in use and is unloaded when not in use.
old-location : stream\bus_interface_reference.htm
old-project : stream
ms.assetid : 17c2c46c-ff79-4c80-82c9-c49b18426789
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : BUS_INTERFACE_REFERENCE, BUS_INTERFACE_REFERENCE, *PBUS_INTERFACE_REFERENCE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BUS_INTERFACE_REFERENCE
req.alt-loc : ks.h
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
req.typenames : BUS_INTERFACE_REFERENCE, *PBUS_INTERFACE_REFERENCE
---

# BUS_INTERFACE_REFERENCE structure
A software device enumerator exports this interface to allow drivers to reference count physical device objects (PDOs) such that the device remains active while in use and is unloaded when not in use.

## Syntax
````
typedef struct {
  INTERFACE                  Interface;
  PFNREFERENCEDEVICEOBJECT   ReferenceDeviceObject;
  PFNDEREFERENCEDEVICEOBJECT DereferenceDeviceObject;
  PFNQUERYREFERENCESTRING    QueryReferenceString;
} BUS_INTERFACE_REFERENCE, *PBUS_INTERFACE_REFERENCE;
````

## Members

        
            `DereferenceDeviceObject`

            Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567170">KStrDereferenceDeviceObject</a> routine.
        
            `Interface`

            Specifies the exported <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>.
        
            `QueryReferenceString`

            Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567193">KStrQueryReferenceString</a> routine.
        
            `ReferenceDeviceObject`

            Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567198">KStrReferenceDeviceObject</a> routine.

    ## Remarks
        A driver obtains a BUS_INTERFACE_REFERENCE interface by creating and sending an IRP_MJ_PNP request that specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> minor function code. To do this, the driver should:

Allocate and zero-fill a BUS_INTERFACE_REFERENCE structure from the paged memory pool.

Create an IRP for the query interface request and get the next stack location for the new IRP.

In the new stack location, provide a pointer to the new BUS_INTERFACE_REFERENCE structure in the <b>Parameters.QueryInterface.Interface</b> member.

Set a completion routine and send the request down the driver stack.

If your request is successful, the system fills in the BUS_INTERFACE_REFERENCE structure pointed to by <b>Parameters.QueryInterface.Interface</b>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |