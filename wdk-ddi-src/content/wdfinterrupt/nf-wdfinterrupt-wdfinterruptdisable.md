---
UID: NF:wdfinterrupt.WdfInterruptDisable
title: WdfInterruptDisable function
author: windows-driver-content
description: The WdfInterruptDisable method disables a specified device interrupt by calling the driver's EvtInterruptDisable callback function.
old-location: wdf\wdfinterruptdisable.htm
old-project: wdf
ms.assetid: 8ece6a3f-2f25-4143-8f0e-c65c02794cc4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFInterruptObjectRef_05ca577a-87b3-419a-a3f8-ee57b0765701.xml, WdfInterruptDisable, WdfInterruptDisable method, kmdf.wdfinterruptdisable, wdf.wdfinterruptdisable, wdfinterrupt/WdfInterruptDisable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfInterruptDisable
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---


# WdfInterruptDisable function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptDisable</b> method disables a specified device interrupt by calling the driver's <a href="https://msdn.microsoft.com/a9d5e3cd-2e95-4ad6-9380-64fe4df9e27f">EvtInterruptDisable</a> callback function.

## Syntax

```
void WdfInterruptDisable(
  WDFINTERRUPT Interrupt
);
```

## Parameters

`Interrupt`

A handle to a framework interrupt object.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Most framework-based drivers don't need to call <b>WdfInterruptDisable</b>, because the framework calls the driver's <a href="https://msdn.microsoft.com/a9d5e3cd-2e95-4ad6-9380-64fe4df9e27f">EvtInterruptDisable</a> callback function each time the device leaves its working (D0) state.

For <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt objects</a>, the framework calls <b>WdfInterruptDisable</b> at PASSIVE_LEVEL.

Do not call <b>WdfInterruptDisable</b> from an arbitrary thread context,  such as a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

The following code example disables the device interrupt that is associated with a specified interrupt object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfInterruptDisable(Interrupt);</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfinterrupt.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="https://msdn.microsoft.com/a9d5e3cd-2e95-4ad6-9380-64fe4df9e27f">EvtInterruptDisable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547354">WdfInterruptEnable</a>