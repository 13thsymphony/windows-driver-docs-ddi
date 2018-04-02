---
UID: NC:wdfdevice.EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE
title: EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE
author: windows-driver-content
description: The EvtDeviceWdmPrePoFxUnregisterDevice callback function performs device-specific operations before the framework deletes a specified registration with the power framework.
old-location: wdf\evtdevicewdmprepofxunregisterdevice.htm
old-project: wdf
ms.assetid: D663C47D-C59E-4210-84D8-9773A3003990
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE, EvtDeviceWdmPrePoFxUnregisterDevice, EvtDeviceWdmPrePoFxUnregisterDevice callback function, kmdf.evtdevicewdmprepofxunregisterdevice, wdf.evtdevicewdmprepofxunregisterdevice, wdfdevice/EvtDeviceWdmPrePoFxUnregisterDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
-	UserDefined
api_location:
-	Wdfdevice.h
api_name:
-	EvtDeviceWdmPrePoFxUnregisterDevice
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---


# EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE callback function
<p class="CCE_Message">[Applies to KMDF only]


   The 
  <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function performs device-specific operations before the framework deletes a specified registration with the power framework.

## Syntax

```
EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE EvtWdfdeviceWdmPrePoFxUnregisterDevice;

void EvtWdfdeviceWdmPrePoFxUnregisterDevice(
  WDFDEVICE Device,
  POHANDLE PoHandle
)
{...}
```

## Parameters

`Device`

A handle to a framework device object.

`PoHandle`

A handle that represents the device’s registration with the power framework.


## Return Value

This callback function does not return a value.

## Remarks

The <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function applies only to single-component devices.

To register an <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451097">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

A driver can provide this callback function if it must perform any additional operations before the framework unregisters the specified POHANDLE.

 After the driver has returned from this callback, it is no longer safe to use this POHANDLE.


#### Examples

To define an <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function that is named <i>MyDeviceWdmPrePoFxUnregisterDevice</i>, use the <b>EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE  MyDeviceWdmPrePoFxUnregisterDevice;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyDeviceWdmPrePoFxUnregisterDevice (
   WDFDEVICE Device,
   POHANDLE PoHandle
   );
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/4CE227F5-9ED4-4484-AFBF-44D1260EB99D">EvtDeviceWdmPostPoFxRegisterDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451097">WdfDeviceWdmAssignPowerFrameworkSettings</a>