---
UID : NS:swenum._BUS_INTERFACE_SWENUM
title : _BUS_INTERFACE_SWENUM
author : windows-driver-content
description : The BUS_INTERFACE_SWENUM structure describes the demand-load bus enumerator object's interface.
old-location : stream\bus_interface_swenum.htm
old-project : stream
ms.assetid : 7e667dd9-8ed1-49ef-a6ef-0d079d41db86
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _BUS_INTERFACE_SWENUM, *PBUS_INTERFACE_SWENUM, BUS_INTERFACE_SWENUM
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : swenum.h
req.include-header : Swenum.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BUS_INTERFACE_SWENUM
req.alt-loc : swenum.h
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
req.typenames : "*PBUS_INTERFACE_SWENUM, BUS_INTERFACE_SWENUM"
req.product : Windows 10 or later.
---

# _BUS_INTERFACE_SWENUM structure
The BUS_INTERFACE_SWENUM structure describes the demand-load bus enumerator object's interface.

## Syntax
````
typedef struct _BUS_INTERFACE_SWENUM {
  INTERFACE                  Interface;
  PFNREFERENCEDEVICEOBJECT   ReferenceDeviceObject;
  PFNDEREFERENCEDEVICEOBJECT DereferenceDeviceObject;
  PFNQUERYREFERENCESTRING    QueryReferenceString;
} BUS_INTERFACE_SWENUM, *PBUS_INTERFACE_SWENUM;
````

## Members

        
            `DereferenceDeviceObject`

            Pointer to a driver-supplied <a href="..\swenum\nf-swenum-ksdereferencesoftwarebusobject.md">KsDereferenceSoftwareBusObject</a> routine.
        
            `Interface`

            Specifies the exported <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>.
        
            `QueryReferenceString`

            Pointer to a driver-supplied <a href="..\swenum\nf-swenum-ksquerysoftwarebusinterface.md">KsQuerySoftwareBusInterface</a> routine.
        
            `ReferenceDeviceObject`

            Pointer to a driver-supplied <a href="..\swenum\nf-swenum-ksreferencesoftwarebusobject.md">KsReferenceSoftwareBusObject</a> routine.

    ## Remarks
        A driver obtains a BUS_INTERFACE_SWENUM interface by creating and sending an IRP_MJ_PNP request that specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> minor function code. To do this, the driver should:

Allocate and zero-fill a BUS_INTERFACE_SWENUM structure from the paged memory pool.

Create an IRP for the query interface request and get the next stack location for the new IRP.

In the new stack location, provide a pointer to the new BUS_INTERFACE_SWENUM structure in the <b>Parameters.QueryInterface.Interface</b> member.

Set a completion routine and send the request down the driver stack.

If your request is successful, the system fills in the BUS_INTERFACE_SWENUM structure pointed to by <b>Parameters.QueryInterface.Interface</b>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | swenum.h (include Swenum.h) |