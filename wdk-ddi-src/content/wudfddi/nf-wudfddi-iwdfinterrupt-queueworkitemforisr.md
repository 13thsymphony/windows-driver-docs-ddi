---
UID: NF:wudfddi.IWDFInterrupt.QueueWorkItemForIsr
title: IWDFInterrupt::QueueWorkItemForIsr method
author: windows-driver-content
description: The QueueWorkItemForIsr method queues a work item to process interrupt-related work outside of the interrupt service routine.
old-location: wdf\iwdfinterrupt_queueworkitemforisr.htm
old-project: wdf
ms.assetid: 5C6DC011-4032-4DB6-AE17-88E510DF9A3A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFInterrupt, IWDFInterrupt interface, QueueWorkItemForIsr method, IWDFInterrupt::QueueWorkItemForIsr, QueueWorkItemForIsr method, QueueWorkItemForIsr method, IWDFInterrupt interface, QueueWorkItemForIsr,IWDFInterrupt.QueueWorkItemForIsr, umdf.iwdfinterrupt_queueworkitemforisr, wdf.iwdfinterrupt_queueworkitemforisr, wudfddi/IWDFInterrupt::QueueWorkItemForIsr
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
-	IWDFInterrupt.QueueWorkItemForIsr
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# QueueWorkItemForIsr method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>QueueWorkItemForIsr</b> method queues a work item to process interrupt-related work outside of the interrupt service routine.

## Syntax

````
BOOLEAN QueueWorkItemForIsr();
````

## Parameters

This function has no parameters.

## Return Value

The method returns TRUE if a work item was successfully queued. If a work item is already in the queue, the method returns FALSE.

## Remarks

The driver provides a pointer to its <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_workitem.md">OnInterruptWorkItem</a> callback function when it calls  <a href="https://msdn.microsoft.com/EE68BED8-5FDC-4590-8E95-B228F1DFD32D">IWDFDevice3::CreateInterrupt</a> to create the interrupt object.

For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.

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



<a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_workitem.md">OnInterruptWorkItem</a>



<a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a>