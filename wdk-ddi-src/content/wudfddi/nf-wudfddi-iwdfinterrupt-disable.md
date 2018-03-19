---
UID: NF:wudfddi.IWDFInterrupt.Disable
title: IWDFInterrupt::Disable method
author: windows-driver-content
description: The Disable method disables a specified device interrupt by calling the driver's OnInterruptDisable callback function.
old-location: wdf\iwdfinterrupt_disable.htm
old-project: wdf
ms.assetid: D87C868D-9538-4752-AEBD-2A15E53628CF
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Disable method, Disable method, IWDFInterrupt interface, Disable,IWDFInterrupt.Disable, IWDFInterrupt, IWDFInterrupt interface, Disable method, IWDFInterrupt::Disable, umdf.iwdfinterrupt_disable, wdf.iwdfinterrupt_disable, wudfddi/IWDFInterrupt::Disable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFInterrupt.Disable
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# Disable method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Disable</b> method disables a specified device interrupt by calling the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_disable.md">OnInterruptDisable</a> callback function.

## Syntax

````
void Disable();
````

## Parameters

This function has no parameters.

## Return Value

This method does not return a value.

## Remarks

Most UMDF drivers do not need to call <b>IWDFInterrupt::Disable</b>, because the framework calls the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_disable.md">OnInterruptDisable</a> callback function each time the device leaves its working (D0) state.



For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.


#### Examples

The following code example disables the device interrupt that is associated with a specified interrupt object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>pIWdfInterrupt-&gt;Disable();</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfinterrupt.md">IWDFInterrupt</a>



<a href="https://msdn.microsoft.com/605C58C2-9A4F-4185-BB5C-95C9F5180C05">IWDFInterrupt::Enable</a>