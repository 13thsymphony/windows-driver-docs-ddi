---
UID: NF:wdfdpc.WDF_DPC_CONFIG_INIT
title: WDF_DPC_CONFIG_INIT function
author: windows-driver-content
description: The WDF_DPC_CONFIG_INIT function initializes a driver's WDF_DPC_CONFIG structure.
old-location: wdf\wdf_dpc_config_init.htm
old-project: wdf
ms.assetid: 12b34b79-0154-4b25-83e7-b15642154b05
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdpc/WDF_DPC_CONFIG_INIT, kmdf.wdf_dpc_config_init, DFDpcObjectRef_ba15c593-3f2a-4e7f-9a58-a550ca47ccc1.xml, wdf.wdf_dpc_config_init, WDF_DPC_CONFIG_INIT function, WDF_DPC_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdpc.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdpc.h
apiname:
-	WDF_DPC_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---


# WDF_DPC_CONFIG_INIT function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DPC_CONFIG_INIT</b> function initializes a driver's <a href="..\wdfdpc\ns-wdfdpc-_wdf_dpc_config.md">WDF_DPC_CONFIG</a> structure.

## Syntax

````
VOID WDF_DPC_CONFIG_INIT(
  _Out_ PWDF_DPC_CONFIG Config,
  _In_  PFN_WDF_DPC     EvtDpcFunc
);
````

## Parameters

`Config`

A pointer to a driver-allocated <a href="..\wdfdpc\ns-wdfdpc-_wdf_dpc_config.md">WDF_DPC_CONFIG</a> structure.

`EvtDpcFunc`

A pointer to a driver-supplied <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function.


## Return Value

None

## Remarks

The <b>WDF_DPC_CONFIG_INIT</b> function stores the specified <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> pointer and sets the <b>AutomaticSerialization</b> member of the WDF_DPC_CONFIG structure to <b>TRUE</b>.


#### Examples

For a code example that uses the <b>WDF_DPC_CONFIG_INIT</b> function, see <a href="..\wdfdpc\nf-wdfdpc-wdfdpccreate.md">WdfDpcCreate</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdpc.h (include Wdf.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdfdpc\ns-wdfdpc-_wdf_dpc_config.md">WDF_DPC_CONFIG</a>



<a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DPC_CONFIG_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>