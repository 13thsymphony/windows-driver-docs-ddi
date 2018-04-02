---
UID: NF:portcls.IPortWMIRegistration.RegisterWMIProvider
title: IPortWMIRegistration::RegisterWMIProvider method
author: windows-driver-content
description: The RegisterWMIProvider method registers the Event Tracing for Windows (ETW) capability of the miniport driver with PortCls.
old-location: audio\iportwmiregistration_registerwmiprovider.htm
old-project: audio
ms.assetid: 5c092cbd-ef05-4b3d-ac9f-20f2fbf2c37c
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPortWMIRegistration, IPortWMIRegistration interface [Audio Devices], RegisterWMIProvider method, IPortWMIRegistration::RegisterWMIProvider, RegisterWMIProvider method [Audio Devices], RegisterWMIProvider method [Audio Devices], IPortWMIRegistration interface, RegisterWMIProvider,IPortWMIRegistration.RegisterWMIProvider, audio.iportwmiregistration_registerwmiprovider, audmp-routines_3a73bed7-3a9f-4be2-8d15-33f707714c94.xml, portcls/IPortWMIRegistration::RegisterWMIProvider
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
-	Portcls.h
api_name:
-	IPortWMIRegistration.RegisterWMIProvider
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IPortWMIRegistration::RegisterWMIProvider method
The <code>RegisterWMIProvider</code> method registers the <a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a> (ETW) capability of the miniport driver with PortCls.

## Syntax

```
NTSTATUS RegisterWMIProvider(
  PDEVICE_OBJECT ,
  PVOID          
);
```

## Parameters

`Arg1`



`Arg1`




## Return Value

The <code>RegisterWMIProvider</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## Remarks

For more information about ETW, see <a href="http://go.microsoft.com/fwlink/p/?linkid=154129">Improve Debugging And Performance Tuning With ETW</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | PASSIVE_LEVEL. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536935">IPortWMIRegistration</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=154129">Improve Debugging And Performance Tuning With ETW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565813">WMILIB_CONTEXT</a>