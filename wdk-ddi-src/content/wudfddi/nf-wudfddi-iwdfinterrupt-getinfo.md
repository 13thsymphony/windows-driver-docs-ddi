---
UID: NF:wudfddi.IWDFInterrupt.GetInfo
title: IWDFInterrupt::GetInfo method
author: windows-driver-content
description: The GetInfo method retrieves information about a specified interrupt.
old-location: wdf\iwdfinterrupt_getinfo.htm
old-project: wdf
ms.assetid: 744D0FFE-6D3C-4AED-8935-63EE9B0AFA0F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetInfo method, GetInfo method, IWDFInterrupt interface, GetInfo,IWDFInterrupt.GetInfo, IWDFInterrupt, IWDFInterrupt interface, GetInfo method, IWDFInterrupt::GetInfo, umdf.iwdfinterrupt_getinfo, wdf.iwdfinterrupt_getinfo, wudfddi/IWDFInterrupt::GetInfo
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
-	IWDFInterrupt.GetInfo
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# GetInfo method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInfo</b> method retrieves information about a specified interrupt.

## Syntax

````
void GetInfo(
   WDF_INTERRUPT_INFO *Info
);
````

## Parameters

`InterruptInfo`




## Return Value

This method does not return a value.

## Remarks

The <b>GetInfo</b> method can obtain interrupt information only if your driver calls it after the framework has called the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439734">OnPrepareHardware</a> callback function and before the framework has called the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439739">OnReleaseHardware</a> callback function.

For information about the order in which a driver's callback functions are called, see <a href="https://msdn.microsoft.com/ca36eee5-482c-4cfe-a515-be9d3743e241">PnP and Power Management Scenarios in UMDF</a>.

For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
IWDFInterrupt* pInterrupt;
WDF_INTERRUPT_INFO  Info;

WDF_INTERRUPT_INFO_INIT(&amp;Info);

pInterrupt&gt;GetInfo(&amp;Info);
</pre>
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



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439734">OnPrepareHardware</a>



<a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_info_init.md">WDF_INTERRUPT_INFO_INIT</a>



<a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439739">OnReleaseHardware</a>