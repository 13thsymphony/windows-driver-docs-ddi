---
UID: NF:portcls.IPortClsPower.SetIdlePowerManagement
title: IPortClsPower::SetIdlePowerManagement method
author: windows-driver-content
description: The SetIdlePowerManagement method provides a way for the adapter driver to opt in or opt out of idle state detection.
old-location: audio\iportclspower_setidlepowermanagement.htm
old-project: audio
ms.assetid: ccef350c-7c46-43fa-8834-b0d712d9cf38
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPortClsPower, IPortClsPower interface [Audio Devices], SetIdlePowerManagement method, IPortClsPower::SetIdlePowerManagement, SetIdlePowerManagement method [Audio Devices], SetIdlePowerManagement method [Audio Devices], IPortClsPower interface, SetIdlePowerManagement,IPortClsPower.SetIdlePowerManagement, audio.iportclspower_setidlepowermanagement, audmp-routines_909c6232-f96f-4487-a51e-a127dc9ad317.xml, portcls/IPortClsPower::SetIdlePowerManagement
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
req.irql: PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortClsPower.SetIdlePowerManagement
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IPortClsPower::SetIdlePowerManagement method
The <code>SetIdlePowerManagement</code> method provides a way for the adapter driver to opt in or opt out of idle state detection.

## Syntax

```
NTSTATUS SetIdlePowerManagement(
  PDEVICE_OBJECT _DeviceObject,
  BOOLEAN        _bEnabled
);
```

## Parameters

`_DeviceObject`

Specifies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.

`_bEnabled`

Specifies a Boolean variable that indicates whether idle state detection is enabled or disabled.


## Return Value

The <code>SetIdlePowerManagement</code> method returns STATUS_SUCCESS if the call was successful. Otherwise, it returns the appropriate error code.

## Remarks

When the <i>bEnabled</i> parameter is set to <b>TRUE</b>, it indicates that the adapter driver has enabled idle state detection. When the system determines that the adapter is idle, the adapter can be put into the sleep state to save power. If the adapter was not designed to suppress the popping sound that is normally associated with power-up, it is possible that the adapter can experience a popping effect when it comes out of the sleep state.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | PASSIVE_LEVEL. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536844">IPortClsPower</a>



<a href="https://msdn.microsoft.com/43721EC9-4901-4C68-9CCC-E0A71BF2200E">Immediate Idle Timeout Opt-in</a>