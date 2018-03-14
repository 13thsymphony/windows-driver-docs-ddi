---
UID: NF:wudfinterrupt.WUDF_INTERRUPT_CONFIG_INIT
title: WUDF_INTERRUPT_CONFIG_INIT function
author: windows-driver-content
description: The WUDF_INTERRUPT_CONFIG_INIT function initializes a WUDF_INTERRUPT_CONFIG structure.
old-location: wdf\wudf_interrupt_config_init.htm
old-project: wdf
ms.assetid: 71011FDF-547E-4FF0-9015-E8E09FDF950E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WUDF_INTERRUPT_CONFIG_INIT, WUDF_INTERRUPT_CONFIG_INIT function, umdf.wudf_interrupt_config_init, wdf.wudf_interrupt_config_init, wudfinterrupt/WUDF_INTERRUPT_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfinterrupt.h
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
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfinterrupt.h
api_name:
-	WUDF_INTERRUPT_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---


# WUDF_INTERRUPT_CONFIG_INIT function
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WUDF_INTERRUPT_CONFIG_INIT</b> function initializes a <a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a> structure.

## Syntax

````
void WUDF_INTERRUPT_CONFIG_INIT(
  _Out_    PWUDF_INTERRUPT_CONFIG      Configuration,
  _In_     PFN_WUDF_INTERRUPT_NOTIFY   OnInterruptIsr,
  _In_opt_ PFN_WUDF_INTERRUPT_WORKITEM OnInterruptWorkItem
);
````

## Parameters

`Configuration`

A pointer to a <a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a> structure.

`OnInterruptIsr`

A pointer to the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_isr.md">OnInterruptIsr</a> event callback function.

`OnInterruptWorkItem`

A pointer to the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_workitem.md">OnInterruptWorkItem</a> event callback function, or NULL.


## Return Value

This function does not return a value.

## Remarks

The <b>WUDF_INTERRUPT_CONFIG_INIT</b> function zeros the specified <a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a> structure and sets its <b>Size</b> member to the structure's size. It also stores the specified callback function pointer(s).

<b>WUDF_INTERRUPT_CONFIG_INIT</b> initializes the configuration structure's <b>ShareVector</b> member to <b>WdfUseDefault</b> and the <b>AutomaticSerialization</b> member to FALSE.


#### Examples

For a code example that uses <b>WUDF_INTERRUPT_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/EE68BED8-5FDC-4590-8E95-B228F1DFD32D">IWDFDevice3::CreateInterrupt</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfinterrupt.h |