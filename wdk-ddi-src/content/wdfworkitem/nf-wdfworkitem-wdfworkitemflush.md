---
UID : NF:wdfworkitem.WdfWorkItemFlush
title : WdfWorkItemFlush function
author : windows-driver-content
description : The WdfWorkItemFlush method returns after a specified work item has been serviced.
old-location : wdf\wdfworkitemflush.htm
old-project : wdf
ms.assetid : 5868dd01-17ba-4edf-b665-c90d2b1aa2ba
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfWorkItemFlush
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfworkitem.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.alt-api : WdfWorkItemFlush
req.alt-loc : Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PWDF_WMI_PROVIDER_CONFIG, WDF_WMI_PROVIDER_CONFIG"
req.product : Windows 10 or later.
---


# WdfWorkItemFlush function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfWorkItemFlush</b> method returns after a specified work item has been serviced.

## Syntax

````
VOID WdfWorkItemFlush(
  _In_ WDFWORKITEM WorkItem
);
````

## Parameters

`WorkItem`

A handle to a framework work-item object that is obtained from a previous call to <a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemcreate.md">WdfWorkItemCreate</a>.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

If your driver calls the <b>WdfWorkItemFlush</b> method, the method does not return until a system worker thread has removed the specified work item from the work-item queue and called the driver's <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function, and the <i>EvtWorkItem</i> callback function has subsequently returned after processing the work item.

Most drivers that use work items do not need to call <b>WdfWorkItemFlush</b>. A driver might call <b>WdfWorkItemFlush</b> if it must synchronize completion of work items with the removal of a remote I/O target. In this case, the driver can call <b>WdfWorkItemFlush</b> from within its <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function. 

For more information about work items, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.

The following code example is an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function from the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">Toaster</a> sample driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfworkitem.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWorkItemFlush method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>