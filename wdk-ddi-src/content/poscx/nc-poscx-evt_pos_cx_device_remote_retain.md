---
UID : NC:poscx.EVT_POS_CX_DEVICE_REMOTE_RETAIN
title : EVT_POS_CX_DEVICE_REMOTE_RETAIN
author : windows-driver-content
description : The EVT_POS_CX_DEVICE_REMOTE_RETAIN callback is called whenever PosCx attempts to hold onto a claim on a network device and allows the driver to do additional work.
old-location : pos\evt_pos_cx_device_remote_retain.htm
old-project : pos
ms.assetid : 9B23DB23-D995-4737-9302-872F2144823D
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : pos.evt_pos_cx_device_remote_retain, EvtPosCxDeviceRemoteRetain callback function, EvtPosCxDeviceRemoteRetain, EVT_POS_CX_DEVICE_REMOTE_RETAIN, EVT_POS_CX_DEVICE_REMOTE_RETAIN, poscx/EvtPosCxDeviceRemoteRetain
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : poscx.h
req.include-header : Poscx.h
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
req.typenames : PCFILTER_DESCRIPTOR, *PPCFILTER_DESCRIPTOR
req.product : Windows 10 or later.
---


# EVT_POS_CX_DEVICE_REMOTE_RETAIN function
The 
  EVT_POS_CX_DEVICE_REMOTE_RETAIN callback is called whenever PosCx attempts to hold onto a claim
on a network device and allows the driver to do additional work. This callback is typically only used with network connected devices that require additional logic for handling ownership transitions.

## Syntax

```
EVT_POS_CX_DEVICE_REMOTE_RETAIN EvtPosCxDeviceRemoteRetain;

_IRQL_requires_same_ NTSTATUS EvtPosCxDeviceRemoteRetain(
  WDFDEVICE device,
  ULONG deviceInterfaceTag
)
{...}
```

## Parameters

`device`

A handle to a framework device object that represents the device.

`deviceInterfaceTag`

An identifier used to specify which interface is being retained in a multi-function device.  For a single-interface device, this value should be 0.


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE.

If the driver is unable to complete the remote retain transaction, it should return STATUS_ACCESS_DENIED so that the failure will bubble up to the application.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | poscx.h (include Poscx.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |