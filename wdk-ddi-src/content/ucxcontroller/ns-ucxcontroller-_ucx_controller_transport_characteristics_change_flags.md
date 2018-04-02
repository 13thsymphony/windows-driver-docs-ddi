---
UID: NS:ucxcontroller._UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
title: "_UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS"
author: windows-driver-content
description: Defines flags for the transport characteristics changes. This structure is used in the EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION callback function.
old-location: buses\ucx_controller_transport_characteristics_change_flags.htm
old-project: usbref
ms.assetid: B5D6BBE4-2FFF-41CB-B747-AA3C6CE9064E
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS, PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS union pointer [Buses], UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS, UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS union [Buses], _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS, buses.ucx_controller_transport_characteristics_change_flags, ucxcontroller/PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS, ucxcontroller/UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
-	UcxController.h
api_name:
-	UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
product:
- Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
req.product: Windows 10 or later.
---

# _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS structure
Defines flags for the transport characteristics changes. This structure is used in the <a href="https://msdn.microsoft.com/559D2215-B78C-41EA-9E2C-6E67AE5276BE">EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION</a> callback function.

## Syntax
```
typedef struct _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS {
  ULONG  AsUlong32;
  struct {
    ULONG  : 1 CurrentRoundtripLatencyChanged;
    ULONG  : 1 CurrentTotalBandwidthChanged;
  } Flags;
  struct {
    ULONG  : 1 CurrentRoundtripLatencyChanged;
    ULONG  : 1 CurrentTotalBandwidthChanged;
  };
} UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS;
```

## Members


`AsUlong32`

Reserved.

`Flags`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | ucxcontroller.h (include Ucxclass.h) |

## See Also

<a href="https://msdn.microsoft.com/559D2215-B78C-41EA-9E2C-6E67AE5276BE">EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION</a>