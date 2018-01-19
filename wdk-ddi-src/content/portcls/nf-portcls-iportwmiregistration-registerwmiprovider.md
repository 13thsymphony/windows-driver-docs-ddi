---
UID : NF:portcls.IPortWMIRegistration.RegisterWMIProvider
title : IPortWMIRegistration::RegisterWMIProvider method
author : windows-driver-content
description : The RegisterWMIProvider method registers the Event Tracing for Windows (ETW) capability of the miniport driver with PortCls.
old-location : audio\iportwmiregistration_registerwmiprovider.htm
old-project : audio
ms.assetid : 5c092cbd-ef05-4b3d-ac9f-20f2fbf2c37c
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IPortWMIRegistration, IPortWMIRegistration::RegisterWMIProvider, RegisterWMIProvider
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
req.alt-api : IPortWMIRegistration.RegisterWMIProvider
req.alt-loc : Portcls.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL.
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# RegisterWMIProvider method
The <code>RegisterWMIProvider</code> method registers the <a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a> (ETW) capability of the miniport driver with PortCls.

## Syntax

````
NTSTATUS RegisterWMIProvider(
  [in] pDeviceObject      pDeviceObject,
  [in] MiniportWmiContext MiniportWmiContext
);
````

## Parameters

``



``




## Return Value

The <code>RegisterWMIProvider</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## Remarks

For more information about ETW, see <a href="http://go.microsoft.com/fwlink/p/?linkid=154129">Improve Debugging And Performance Tuning With ETW</a>.

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

<dl>
<dt>
<a href="..\portcls\nn-portcls-iportwmiregistration.md">IPortWMIRegistration</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a>
</dt>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=154129">Improve Debugging And Performance Tuning With ETW</a></dt>
<dt>
<a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWMIRegistration::RegisterWMIProvider method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>