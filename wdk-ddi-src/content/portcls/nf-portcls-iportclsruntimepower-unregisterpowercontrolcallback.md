---
UID: NF:portcls.IPortClsRuntimePower.UnregisterPowerControlCallback
title: IPortClsRuntimePower::UnregisterPowerControlCallback method
author: windows-driver-content
description: The port class driver (PortCls) uses the UnregisterPowerControlCallback method to unregister a power control callback.
old-location: audio\iportclsruntimepower_unregisterpowercontrolcallback.htm
old-project: audio
ms.assetid: F7E83587-0499-4D56-8D34-5513454FFEE2
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: UnregisterPowerControlCallback method [Audio Devices], IPortClsRuntimePower interface, IPortClsRuntimePower::UnregisterPowerControlCallback, UnregisterPowerControlCallback method [Audio Devices], IPortClsRuntimePower, UnregisterPowerControlCallback, IPortClsRuntimePower interface [Audio Devices], UnregisterPowerControlCallback method, audio.iportclsruntimepower_unregisterpowercontrolcallback, portcls/IPortClsRuntimePower::UnregisterPowerControlCallback
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
req.lib: portcls.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Portcls.h
apiname:
-	IPortClsRuntimePower.UnregisterPowerControlCallback
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---


# UnregisterPowerControlCallback method
The port class driver (PortCls) uses the <code>UnregisterPowerControlCallback</code>  method to unregister a power control callback.

## Syntax

````
NTSTATUS UnregisterPowerControlCallback(
  [in] PDEVICE_OBJECT DeviceObject
);
````

## Parameters

`_DeviceObject`

The device object.


## Return Value

The <code>UnregisterPowerControlCallback</code> method returns STATUS_SUCCESS, if the call is successful. Otherwise, it returns the appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 7 Windows 7 |
| **Target Platform** | Universal |
| **Header** | portcls.h |
| **Library** | portcls.h |

## See Also

<a href="..\portcls\nn-portcls-iportclsruntimepower.md">IPortClsRuntimePower</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsRuntimePower::UnregisterPowerControlCallback method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>