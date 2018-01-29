---
UID : NF:portcls.IPortClsPower.RegisterAdapterPowerManagement
title : IPortClsPower::RegisterAdapterPowerManagement method
author : windows-driver-content
description : The RegisterAdapterPowerManagement method registers the power management interface of the adapter with PortCls.
old-location : audio\iportclspower_registeradapterpowermanagement.htm
old-project : audio
ms.assetid : f4eb9d18-4352-47e2-bd5f-256e1fa831d3
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IPortClsPower interface [Audio Devices], RegisterAdapterPowerManagement method, IPortClsPower::RegisterAdapterPowerManagement, portcls/IPortClsPower::RegisterAdapterPowerManagement, audio.iportclspower_registeradapterpowermanagement, RegisterAdapterPowerManagement, RegisterAdapterPowerManagement method [Audio Devices], IPortClsPower interface, RegisterAdapterPowerManagement method [Audio Devices], audmp-routines_9c179fd9-d332-478d-a114-469dc1c746fc.xml, IPortClsPower
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : Portcls.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 7 and later versions of Windows.
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
req.irql : PASSIVE_LEVEL.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# RegisterAdapterPowerManagement method
The <code>RegisterAdapterPowerManagement</code> method registers the power management interface of the adapter with PortCls.

## Syntax

````
NTSTATUS RegisterAdapterPowerManagement(
  [in] PUNKNOWN       pUnknown,
  [in] PDEVICE_OBJECT DeviceObject
);
````

## Parameters

`_pUnknown`



`_DeviceObject`




## Return Value

The <code>RegisterAdapterPowerManagement</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error code.

## Remarks

When the <code>RegisterAdapterPowerManagement</code> method registers the power management interface for the adapter with PortCls, it allows the adapter driver to be notified of power state change events.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h (include Portcls.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL. |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="..\portcls\nn-portcls-iadapterpowermanagement2.md">IAdapterPowerManagement2</a>

<a href="..\portcls\nn-portcls-iportclspower.md">IPortClsPower</a>

<a href="..\portcls\nn-portcls-iadapterpowermanagement.md">IAdapterPowerManagement</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsPower::RegisterAdapterPowerManagement method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>