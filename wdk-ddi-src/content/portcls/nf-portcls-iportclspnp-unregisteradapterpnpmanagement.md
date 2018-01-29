---
UID : NF:portcls.IPortClsPnp.UnregisterAdapterPnpManagement
title : IPortClsPnp::UnregisterAdapterPnpManagement method
author : windows-driver-content
description : The UnRegisterAdapterPowerManagement method unregisters the PnP management interface of the adapter from PortCls.
old-location : audio\iportclspnp_unregisteradapterpnpmanagement.htm
old-project : audio
ms.assetid : 7FAA5C88-2846-4C98-A44A-B53A1A7A953C
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IPortClsPnp interface [Audio Devices], UnregisterAdapterPnpManagement method, UnregisterAdapterPnpManagement method [Audio Devices], IPortClsPnp interface, IPortClsPnp, UnregisterAdapterPnpManagement method [Audio Devices], IPortClsPnp::UnregisterAdapterPnpManagement, UnregisterAdapterPnpManagement, portcls/IPortClsPnp::UnregisterAdapterPnpManagement, audio.iportclspnp_unregisteradapterpnpmanagement
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : Portcls.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 10, version 1511 and later versions of Windows.
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
req.lib : portcls.h
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# UnregisterAdapterPnpManagement method
The <code>UnRegisterAdapterPowerManagement</code> method unregisters the PnP management interface of the adapter from PortCls.

## Syntax

````
NTSTATUS UnregisterAdapterPnpManagement(
  [in] PDEVICE_OBJECT DeviceObject
);
````

## Parameters

`DeviceObject`

Specifies a pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter that the PnP management was registered with earlier using <a href="https://msdn.microsoft.com/library/windows/hardware/mt604860">IPortClsPnp::RegisterAdapterPnpManagement</a>.


## Return Value

The <code>UnregisterAdapterPowerManagement</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error code.

## Remarks

For more information,  see <a href="https://msdn.microsoft.com/FCAD7F8B-AA9B-430A-BCAF-04E13FA15382">Implement PnP Rebalance for PortCls Audio Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h (include Portcls.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\portcls\nn-portcls-iportclspnp.md">IPortClsPnp</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt604860">IPortClsPnp::RegisterAdapterPnpManagement</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsPnp::UnregisterAdapterPnpManagement method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>