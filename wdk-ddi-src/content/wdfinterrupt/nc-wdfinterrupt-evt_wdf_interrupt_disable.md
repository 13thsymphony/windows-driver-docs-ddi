---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_DISABLE
title: EVT_WDF_INTERRUPT_DISABLE
author: windows-driver-content
description: A driver's EvtInterruptDisable event callback function disables a specified hardware interrupt.
old-location: wdf\evtinterruptdisable.htm
old-project: wdf
ms.assetid: a9d5e3cd-2e95-4ad6-9380-64fe4df9e27f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFInterruptObjectRef_4dfbc961-e1c4-494e-9e6d-d657fd5d59d9.xml, EVT_WDF_INTERRUPT_DISABLE, EvtInterruptDisable, EvtInterruptDisable callback function, kmdf.evtinterruptdisable, wdf.evtinterruptdisable, wdfinterrupt/EvtInterruptDisable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "(See Remarks section.)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfinterrupt.h
api_name:
-	EvtInterruptDisable
product: Windows
targetos: Windows
req.typenames: WDF_COINSTALLER_INSTALL_OPTIONS, *PWDF_COINSTALLER_INSTALL_OPTIONS
req.product: Windows 10 or later.
---


# EVT_WDF_INTERRUPT_DISABLE callback function
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtInterruptDisable</i> event callback function disables a specified hardware interrupt.

## Syntax

```
EVT_WDF_INTERRUPT_DISABLE EvtWdfInterruptDisable;

NTSTATUS EvtWdfInterruptDisable(
  WDFINTERRUPT Interrupt,
  WDFDEVICE AssociatedDevice
)
{...}
```

## Parameters

`Interrupt`

A handle to a framework interrupt object.

`AssociatedDevice`

A handle to the framework device object that the driver passed to <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>.


## Return Value

The <i>EvtInterruptDisable</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b> if the function encounters no errors. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

## Remarks

To register an <i>EvtInterruptDisable</i> callback function, your driver must place the callback function's address in a <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>.

The framework calls the driver's <i>EvtInterruptDisable</i> callback function each time the device leaves its working (D0) state. Additionally, a driver can cause the framework to call the <i>EvtInterruptDisable</i> callback function by calling <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptdisable.md">WdfInterruptDisable</a>. Note that most framework-based drivers should not call <b>WdfInterruptDisable</b>, because the framework calls the driver's <i>EvtInterruptDisable</i> callback function each time the device leaves its working (D0) state.

Before calling the <i>EvtInterruptDisable</i> callback function, the framework raises the processor's IRQL to the device's DIRQL and acquires the spin lock that the driver specified in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure. 

Beginning with version 1.11 of KMDF, your driver can provide <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a>. If the driver has requested passive-level interrupt handling, then before calling the <i>EvtInterruptDisable</i> function at IRQL = PASSIVE_LEVEL, the framework acquires the passive-level interrupt lock that the driver configured in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure.

Before calling the <i>EvtInterruptDisable</i> callback function, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled.md">EvtDeviceD0ExitPreInterruptsDisabled</a> event callback function at IRQL = PASSIVE_LEVEL.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

To define an <i>EvtInterruptDisable</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtInterruptDisable</i> callback function that is named <i>MyInterruptDisable</i>, use the <b>EVT_WDF_INTERRUPT_DISABLE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_INTERRUPT_DISABLE  MyInterruptDisable;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
 MyInterruptDisable (
    WDFINTERRUPT  Interrupt,
    WDFDEVICE  AssociatedDevice
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_INTERRUPT_DISABLE</b> function type is defined in the Wdfinterrupt.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_INTERRUPT_DISABLE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfinterrupt.h (include Wdf.h) |
| **IRQL** | "(See Remarks section.)" |

## See Also

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a>



<a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled.md">EvtDeviceD0ExitPreInterruptsDisabled</a>



<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptdisable.md">WdfInterruptDisable</a>



<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_INTERRUPT_DISABLE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>