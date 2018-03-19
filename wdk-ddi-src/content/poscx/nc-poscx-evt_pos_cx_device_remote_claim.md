---
UID: NC:poscx.EVT_POS_CX_DEVICE_REMOTE_CLAIM
title: EVT_POS_CX_DEVICE_REMOTE_CLAIM
author: windows-driver-content
description: The EVT_POS_CX_DEVICE_REMOTE_CLAIM callback is called when the device is transitioning from unclaimed to claimed and allows the driver to do additional work.
old-location: pos\evt_pos_cx_device_remote_claim.htm
old-project: pos
ms.assetid: 3D8907A2-E53E-40D9-870A-AF0EB062E81F
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: EVT_POS_CX_DEVICE_REMOTE_CLAIM, EvtPosCxDeviceRemoteClaim, EvtPosCxDeviceRemoteClaim callback function, pos.evt_pos_cx_device_remote_claim, poscx/EvtPosCxDeviceRemoteClaim
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: poscx.h
req.include-header: Poscx.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	poscx.h
api_name:
-	EvtPosCxDeviceRemoteClaim
product: Windows
targetos: Windows
req.typenames: PCFILTER_DESCRIPTOR, *PPCFILTER_DESCRIPTOR
req.product: Windows 10 or later.
---


# EVT_POS_CX_DEVICE_REMOTE_CLAIM callback function
The 
  EVT_POS_CX_DEVICE_REMOTE_CLAIM callback is called when the device is transitioning from
unclaimed to claimed and allows the driver to do additional work. This callback is typically only used with network connected devices that require additional logic for handling ownership transitions.

<i>EVT_POS_CX_DEVICE_REMOTE_CLAIM</i> and <a href="..\poscx\nc-poscx-evt_pos_cx_device_remote_release.md">EVT_POS_CX_DEVICE_REMOTE_RELEASE</a> add support for remote devices that handle their own claim
semantics.

## Syntax

```
EVT_POS_CX_DEVICE_REMOTE_CLAIM EvtPosCxDeviceRemoteClaim;

_IRQL_requires_same_ NTSTATUS EvtPosCxDeviceRemoteClaim(
  WDFDEVICE device,
  ULONG deviceInterfaceTag
)
{...}
```

## Parameters

`device`

A handle to a framework device object that represents the device.

`deviceInterfaceTag`

An identifier used to specify which interface is being claimed in a multi-function device.  For a single-interface device, this value should be 0.


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE.

If the driver is unable to complete the remote claim transaction, it should return STATUS_ACCESS_DENIED so that the failure will bubble up to the application.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | poscx.h (include Poscx.h) |

## See Also

<a href="..\poscx\nc-poscx-evt_pos_cx_device_remote_release.md">EVT_POS_CX_DEVICE_REMOTE_RELEASE</a>