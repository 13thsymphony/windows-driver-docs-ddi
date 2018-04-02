---
UID: NF:portcls.IPortClsRuntimePower.RegisterPowerControlCallback
title: IPortClsRuntimePower::RegisterPowerControlCallback method
author: windows-driver-content
description: The port class driver (PortCls) uses the RegisterPowerControlCallback method to register a power control callback.
old-location: audio\iportclsruntimepower_registerpowercontrolcallback.htm
old-project: audio
ms.assetid: 1500E2C2-240F-4087-9275-9FD4170B8BED
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPortClsRuntimePower, IPortClsRuntimePower interface [Audio Devices], RegisterPowerControlCallback method, IPortClsRuntimePower::RegisterPowerControlCallback, RegisterPowerControlCallback method [Audio Devices], RegisterPowerControlCallback method [Audio Devices], IPortClsRuntimePower interface, RegisterPowerControlCallback,IPortClsRuntimePower.RegisterPowerControlCallback, audio.iportclsruntimepower_registerpowercontrolcallback, portcls/IPortClsRuntimePower::RegisterPowerControlCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: Windows Server 2003
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
-	COM
api_location:
-	Portcls.h
api_name:
-	IPortClsRuntimePower.RegisterPowerControlCallback
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IPortClsRuntimePower::RegisterPowerControlCallback method
The port class driver (PortCls) uses the <code>RegisterPowerControlCallback</code>  method to register a power control callback.

## Syntax

```
NTSTATUS RegisterPowerControlCallback(
  PDEVICE_OBJECT                      _DeviceObject,
  PCPFNRUNTIME_POWER_CONTROL_CALLBACK _Callback,
  PVOID                               _Context
);
```

## Parameters

`_DeviceObject`

The device object.

`_Callback`

The callback object.

`_Context`

The callback context.


## Return Value

The <code>RegisterPowerControlCallback</code> method returns STATUS_SUCCESS, if the call is successful. Otherwise, it returns the appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 7 Windows Server 2003 |
| **Target Platform** | Universal |
| **Header** | portcls.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265125">IPortClsRuntimePower</a>