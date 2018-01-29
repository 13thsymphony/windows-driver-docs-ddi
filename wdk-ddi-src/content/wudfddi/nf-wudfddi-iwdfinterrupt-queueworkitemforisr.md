---
UID : NF:wudfddi.IWDFInterrupt.QueueWorkItemForIsr
title : IWDFInterrupt::QueueWorkItemForIsr method
author : windows-driver-content
description : The QueueWorkItemForIsr method queues a work item to process interrupt-related work outside of the interrupt service routine.
old-location : wdf\iwdfinterrupt_queueworkitemforisr.htm
old-project : wdf
ms.assetid : 5C6DC011-4032-4DB6-AE17-88E510DF9A3A
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFInterrupt, umdf.iwdfinterrupt_queueworkitemforisr, IWDFInterrupt::QueueWorkItemForIsr, IWDFInterrupt interface, QueueWorkItemForIsr method, wudfddi/IWDFInterrupt::QueueWorkItemForIsr, QueueWorkItemForIsr method, QueueWorkItemForIsr, wdf.iwdfinterrupt_queueworkitemforisr, QueueWorkItemForIsr method, IWDFInterrupt interface
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.11
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wudfddi.h
req.dll : WUDFx.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
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
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_workitem.md">OnInterruptWorkItem</a>

<a href="..\wudfddi\nn-wudfddi-iwdfinterrupt.md">IWDFInterrupt</a>

<a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFInterrupt::QueueWorkItemForIsr method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>