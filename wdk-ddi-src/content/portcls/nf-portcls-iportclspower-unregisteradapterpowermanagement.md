---
UID: NF:portcls.IPortClsPower.UnregisterAdapterPowerManagement
title: IPortClsPower::UnregisterAdapterPowerManagement method
author: windows-driver-content
description: The UnregisterAdapterPowerManagement method unregisters the adapter's power management interface with PortCls.
old-location: audio\iportclspower_unregisteradapterpowermanagement.htm
old-project: audio
ms.assetid: 4c8734b1-d7f5-476b-a85f-1d3f4df888b9
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.iportclspower_unregisteradapterpowermanagement, UnregisterAdapterPowerManagement method [Audio Devices], IPortClsPower interface, IPortClsPower, UnregisterAdapterPowerManagement, portcls/IPortClsPower::UnregisterAdapterPowerManagement, IPortClsPower::UnregisterAdapterPowerManagement, IPortClsPower interface [Audio Devices], UnregisterAdapterPowerManagement method, audmp-routines_3dca5fa9-542d-437d-a2d9-9eef51b5f2ea.xml, UnregisterAdapterPowerManagement method [Audio Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windwows.
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
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IPortClsPower.UnregisterAdapterPowerManagement
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---


# UnregisterAdapterPowerManagement method
The <code>UnregisterAdapterPowerManagement</code> method unregisters the adapter's power management interface with PortCls.

## Syntax

````
NTSTATUS UnregisterAdapterPowerManagement(
  [in] PDEVICE_OBJECT DeviceObject
);
````

## Parameters

`_DeviceObject`

Specifies a pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


## Return Value

The <code>UnregisterAdapterPowerManagement</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error code.

## Remarks

The <code>UnregisterAdapterPowerManagement</code> method unregisters the adapter's power management interface that was registered by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536874">IPortClsPower::RegisterAdapterPowerManagement</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windwows. Available in Windows 7 and later versions of Windwows. |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | portcls.h |
| **IRQL** | PASSIVE_LEVEL. |

## See Also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536874">IPortClsPower::RegisterAdapterPowerManagement</a>



<a href="..\portcls\nn-portcls-iportclspower.md">IPortClsPower</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsPower::UnregisterAdapterPowerManagement method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>