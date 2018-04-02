---
UID: NF:portcls.IPortClsPnp.RegisterAdapterPnpManagement
title: IPortClsPnp::RegisterAdapterPnpManagement method
author: windows-driver-content
description: The RegisterAdapterPowerManagement method registers the PnP management interface of the adapter with PortCls.
old-location: audio\iportclspnp_registeradapterpnpmanagement.htm
old-project: audio
ms.assetid: D9A54562-0ABC-4BEA-A9E3-F1A0A4EBC095
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPortClsPnp, IPortClsPnp interface [Audio Devices], RegisterAdapterPnpManagement method, IPortClsPnp::RegisterAdapterPnpManagement, RegisterAdapterPnpManagement method [Audio Devices], RegisterAdapterPnpManagement method [Audio Devices], IPortClsPnp interface, RegisterAdapterPnpManagement,IPortClsPnp.RegisterAdapterPnpManagement, audio.iportclspnp_registeradapterpnpmanagement, portcls/IPortClsPnp::RegisterAdapterPnpManagement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1511 and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortClsPnp.RegisterAdapterPnpManagement
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IPortClsPnp::RegisterAdapterPnpManagement method
The <code>RegisterAdapterPowerManagement</code> method registers the PnP management interface of the adapter with PortCls.

## Syntax

```
NTSTATUS RegisterAdapterPnpManagement(
  PUNKNOWN       pUnknown,
  PDEVICE_OBJECT DeviceObject
);
```

## Parameters

`pUnknown`

Specifies a pointer to <b>IUnknown</b> of <a href="https://msdn.microsoft.com/library/windows/hardware/mt604850">IAdapterPnpManagement</a>.

`DeviceObject`

Specifies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


## Return Value

The <code>RegisterAdapterPowerManagement</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error code.

## Remarks

When the <code>RegisterAdapterPowerManagement</code> method registers the PnP management interface for the adapter with PortCls, it allows the adapter driver to be notified of PnP state change events.

For more information,  see <a href="https://msdn.microsoft.com/FCAD7F8B-AA9B-430A-BCAF-04E13FA15382">Implement PnP Rebalance for PortCls Audio Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 10, version 1511 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt604859">IPortClsPnp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536876">IPortClsPower::UnregisterAdapterPowerManagement</a>