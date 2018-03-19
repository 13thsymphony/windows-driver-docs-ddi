---
UID: NF:portcls.IPortClsRuntimePower.SendPowerControl
title: IPortClsRuntimePower::SendPowerControl method
author: windows-driver-content
description: The port class driver (PortCls) uses the SendPowerControl method to send power control codes to the audio adapter.
old-location: audio\iportclsruntimepower_sendpowercontrol.htm
old-project: audio
ms.assetid: 04B8EE71-59F9-4DE4-AD36-846632D3EBB4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IPortClsRuntimePower, IPortClsRuntimePower interface [Audio Devices], SendPowerControl method, IPortClsRuntimePower::SendPowerControl, SendPowerControl method [Audio Devices], SendPowerControl method [Audio Devices], IPortClsRuntimePower interface, SendPowerControl,IPortClsRuntimePower.SendPowerControl, audio.iportclsruntimepower_sendpowercontrol, portcls/IPortClsRuntimePower::SendPowerControl
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
-	IPortClsRuntimePower.SendPowerControl
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# SendPowerControl method
The port class driver (PortCls) uses the <code>SendPowerControl</code>  method to send power control codes to the audio adapter.

## Syntax

````
NTSTATUS SendPowerControl(
  [in]            PDEVICE_OBJECT DeviceObject,
  [in]            LPCGUID        PowerControlCode,
  [in, optional]  PVOID          InBuffer,
  [in]            SIZE_T         InBufferSize,
  [out, optional] PVOID          OutBuffer,
  [in]            SIZE_T         OutBufferSize,
  [out, optional] PSIZE_T        BytesReturned
);
````

## Parameters

`_DeviceObject`

The device object.

`_PowerControlCode`

The power control code to be sent to the audio adapter.

`_InBuffer`

The input buffer.

`_InBufferSize`

The size of the input buffer.

`_OutBuffer`

The output buffer.

`_OutBufferSize`

The size of the output buffer.

`_BytesReturned`

The number of bytes returned.


## Return Value

The <code>SendPowerControl</code> method returns STATUS_SUCCESS, if the call is successful. Otherwise, it returns the appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 7 Windows Server 2003 |
| **Target Platform** | Universal |
| **Header** | portcls.h |

## See Also

<a href="..\portcls\nn-portcls-iportclsruntimepower.md">IPortClsRuntimePower</a>