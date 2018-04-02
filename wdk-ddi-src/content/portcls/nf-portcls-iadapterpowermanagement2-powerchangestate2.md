---
UID: NF:portcls.IAdapterPowerManagement2.PowerChangeState2
title: IAdapterPowerManagement2::PowerChangeState2 method
author: windows-driver-content
description: Portcls calls the IAdapterPowerManagement2::PowerChangeState2 method to request a change to the new power state. This request is passed on to the adapter driver.
old-location: audio\iadapterpowermanagement2_powerchangestate2.htm
old-project: audio
ms.assetid: 72068476-5821-4646-88b3-06f3a1917fca
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IAdapterPowerManagement2, IAdapterPowerManagement2 interface [Audio Devices], PowerChangeState2 method, IAdapterPowerManagement2::PowerChangeState2, PowerChangeState2 method [Audio Devices], PowerChangeState2 method [Audio Devices], IAdapterPowerManagement2 interface, PowerChangeState2,IAdapterPowerManagement2.PowerChangeState2, audio.iadapterpowermanagement2_powerchangestate2, audmp-routines_d145e24a-5ef1-44a3-b51b-9ee2c8a89772.xml, portcls/IAdapterPowerManagement2::PowerChangeState2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	COM
api_location:
-	portcls.h
api_name:
-	IAdapterPowerManagement2.PowerChangeState2
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IAdapterPowerManagement2::PowerChangeState2 method
Portcls calls the <code>IAdapterPowerManagement2::PowerChangeState2</code> method to request a change to the new power state. This request is passed on to the adapter driver.

## Syntax

```
void PowerChangeState2(
  DEVICE_POWER_STATE NewDeviceState,
  SYSTEM_POWER_STATE NewSystemState
);
```

## Parameters

`NewDeviceState`

Specifies the new power state that Portcls has requested for the device. This parameter is an enumeration of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a>.

`NewSystemState`

Specifies the new power state that Portcls has requested for the system. This parameter is an enumeration of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564565">SYSTEM_POWER_STATE</a>.


## Return Value

None

## Remarks

A power state indicates the level of power consumption of a device or system. As a result, the level of computing activity is directly affected by the power state of a device or system. 

For more information about system power states, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546941">Handling System Power State Requests</a>. For more information about device power states, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554397">Managing Power for Individual Devices</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546941">Handling System Power State Requests</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536486">IAdapterPowerManagement2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554397">Managing Power for Individual Devices</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564565">SYSTEM_POWER_STATE</a>