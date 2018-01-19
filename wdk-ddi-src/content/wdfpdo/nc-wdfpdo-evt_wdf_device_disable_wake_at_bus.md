---
UID : NC:wdfpdo.EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS
title : EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS
author : windows-driver-content
description : A bus driver's EvtDeviceDisableWakeAtBus event callback function performs bus-level operations that disable the ability of one of the bus's devices to trigger a wake-up signal on the bus.
old-location : wdf\evtdevicedisablewakeatbus.htm
old-project : wdf
ms.assetid : 91ae9694-5020-42ee-b882-a753e9bbe919
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdfpdo.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.alt-api : EvtDeviceDisableWakeAtBus
req.alt-loc : Wdfpdo.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product : Windows 10 or later.
---


# EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS function
<p class="CCE_Message">[Applies to KMDF only]

A bus driver's <i>EvtDeviceDisableWakeAtBus</i> event callback function performs bus-level operations that disable the ability of one of the bus's devices to trigger a wake-up signal on the bus.

## Syntax

```
EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS EvtWdfDeviceDisableWakeAtBus;

void EvtWdfDeviceDisableWakeAtBus(
  WDFDEVICE Device
)
{...}
```

## Parameters

`Device`

A handle to a framework device object.


## Return Value

None

## Remarks

For more information about this callback function, see <a href="https://msdn.microsoft.com/519dcd1a-9975-48b1-a032-04348b903ac5">Supporting System Wake-Up</a>.

To define an <i>EvtDeviceDisableWakeAtBus</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceDisableWakeAtBus</i> callback function that is named <i>MyDeviceDisableWakeAtBus</i>, use the <b>EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS</b> type as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS</b> function type is defined in the Wdfpdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfpdo.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdfpdo\nc-wdfpdo-evt_wdf_device_enable_wake_at_bus.md">EvtDeviceEnableWakeAtBus</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>