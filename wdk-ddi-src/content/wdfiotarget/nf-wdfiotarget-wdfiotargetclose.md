---
UID : NF:wdfiotarget.WdfIoTargetClose
title : WdfIoTargetClose function
author : windows-driver-content
description : The WdfIoTargetClose method closes a specified remote I/O target.
old-location : wdf\wdfiotargetclose.htm
old-project : wdf
ms.assetid : 7de1ce11-a2b3-4d68-b279-4652b822297b
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfIoTargetClose, kmdf.wdfiotargetclose, wdf.wdfiotargetclose, WdfIoTargetClose method, DFIOTargetRef_3ef7f2b7-6919-46d7-b48c-10dc135905d4.xml, PFN_WDFIOTARGETCLOSE, wdfiotarget/WdfIoTargetClose
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfiotarget.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_IO_TARGET_STATE, WDF_IO_TARGET_STATE"
req.product : Windows 10 or later.
---


# WdfIoTargetClose function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetClose</b> method closes a specified remote I/O target.

## Syntax

````
VOID WdfIoTargetClose(
  _In_ WDFIOTARGET IoTarget
);
````

## Parameters

`IoTarget`

A handle to an I/O target object that was obtained from a previous call to <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

After a driver has called <b>WdfIoTargetClose</b>, it can call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a> to reopen the remote I/O target.

Drivers that supply an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_complete.md">EvtIoTargetRemoveComplete</a> callback function must call <b>WdfIoTargetClose</b> from within that callback function.

Before the <b>WdfIoTargetClose</b> method returns, the framework <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">cancels</a> all of the target queue's I/O requests. 

If a driver has finished using a remote I/O target and will not use the target again, and the target has no child request objects that are still pending, the driver can call <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a> without first calling <b>WdfIoTargetClose</b>. The call to <b>WdfObjectDelete</b> will close the remote I/O target, cancel all of the target queue's I/O requests, and delete the I/O target object. (Note that if the remote I/O target's parent object is a device object, the framework closes the target and deletes the target object when it deletes the parent object.) If the target has any child request objects that are still pending, the driver must call <b>WdfIoTargetClose</b> before it can safely call <b>WdfObjectDelete</b>.

For more information about <b>WdfIoTargetClose</b>, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfiotarget.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>

<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_complete.md">EvtIoTargetRemoveComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetClose method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>