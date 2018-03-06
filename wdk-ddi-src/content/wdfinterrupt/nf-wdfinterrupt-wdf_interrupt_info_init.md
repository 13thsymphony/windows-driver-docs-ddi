---
UID: NF:wdfinterrupt.WDF_INTERRUPT_INFO_INIT
title: WDF_INTERRUPT_INFO_INIT function
author: windows-driver-content
description: The WDF_INTERRUPT_INFO_INIT function initializes a WDF_INTERRUPT_INFO structure.
old-location: wdf\wdf_interrupt_info_init.htm
old-project: wdf
ms.assetid: 4c23f270-9ea3-475f-81d8-c003b2aca44b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFInterruptObjectRef_5b885d42-7ce9-4ac2-b97b-c41906298c22.xml, WDF_INTERRUPT_INFO_INIT, WDF_INTERRUPT_INFO_INIT function, kmdf.wdf_interrupt_info_init, wdf.wdf_interrupt_info_init, wdfinterrupt/WDF_INTERRUPT_INFO_INIT
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfinterrupt.h
api_name:
-	WDF_INTERRUPT_INFO_INIT
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---


# WDF_INTERRUPT_INFO_INIT function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_INTERRUPT_INFO_INIT</b> function initializes a <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a> structure.

## Syntax

````
VOID WDF_INTERRUPT_INFO_INIT(
  _Out_ PWDF_INTERRUPT_INFO Info
);
````

## Parameters

`Info`

A pointer to a driver-allocated <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a> structure.


## Return Value

None

## Remarks

The <b>WDF_INTERRUPT_INFO_INIT</b> function zeros the specified <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a> structure and sets the structure's <b>Size</b> member.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

For a code example that uses <b>WDF_INTERRUPT_INFO_INIT</b>, see <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptgetinfo.md">WdfInterruptGetInfo</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfinterrupt.h (include Wdf.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a>

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptgetinfo.md">WdfInterruptGetInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_INFO_INIT function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>