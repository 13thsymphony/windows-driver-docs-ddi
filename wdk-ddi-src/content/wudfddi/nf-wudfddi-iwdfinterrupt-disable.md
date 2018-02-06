---
UID: NF:wudfddi.IWDFInterrupt.Disable
title: IWDFInterrupt::Disable method
author: windows-driver-content
description: The Disable method disables a specified device interrupt by calling the driver's OnInterruptDisable callback function.
old-location: wdf\iwdfinterrupt_disable.htm
old-project: wdf
ms.assetid: D87C868D-9538-4752-AEBD-2A15E53628CF
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFInterrupt interface, Disable method, wdf.iwdfinterrupt_disable, IWDFInterrupt, wudfddi/IWDFInterrupt::Disable, Disable method, Disable method, IWDFInterrupt interface, umdf.iwdfinterrupt_disable, IWDFInterrupt::Disable, Disable
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFInterrupt.Disable
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
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

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |
| **Library** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfinterrupt.md">IWDFInterrupt</a>

<a href="https://msdn.microsoft.com/605C58C2-9A4F-4185-BB5C-95C9F5180C05">IWDFInterrupt::Enable</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFInterrupt::Disable method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>