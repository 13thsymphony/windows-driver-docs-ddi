---
UID : NF:wdfiotarget.WdfIoTargetWdmGetTargetDeviceObject
title : WdfIoTargetWdmGetTargetDeviceObject function
author : windows-driver-content
description : The WdfIoTargetWdmGetTargetDeviceObject method returns a pointer to the Windows Driver Model (WDM) device object that is associated with a specified local or remote I/O target.
old-location : wdf\wdfiotargetwdmgettargetdeviceobject.htm
old-project : wdf
ms.assetid : 199c2fd6-ecff-4b72-b55d-086687989485
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfIoTargetWdmGetTargetDeviceObject
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfiotarget.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.alt-api : WdfIoTargetWdmGetTargetDeviceObject
req.alt-loc : Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product : Windows 10 or later.
---


# WdfIoTargetWdmGetTargetDeviceObject function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoTargetWdmGetTargetDeviceObject</b> method returns a pointer to the Windows Driver Model (WDM) device object that is associated with a specified local or remote I/O target.

## Syntax

````
PDEVICE_OBJECT WdfIoTargetWdmGetTargetDeviceObject(
  _In_ WDFIOTARGET IoTarget
);
````

## Parameters

`IoTarget`

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a> or from a method that a specialized I/O target supplies.


## Return Value

<b>WdfIoTargetWdmGetTargetDeviceObject</b> returns a pointer to a WDM <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Most framework-based drivers do not need to access an I/O target's WDM device object.

The pointer that the <b>WdfIoTargetWdmGetTargetDeviceObject</b> method returns is valid until the driver calls <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetclose.md">WdfIoTargetClose</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcloseforqueryremove.md">WdfIoTargetCloseForQueryRemove</a>, or until the remote I/O target object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the remote I/O target object, and if the object is deleted before the remote I/O target is closed, the pointer is valid until the <i>EvtCleanupCallback</i> function returns.

If the driver attempts to access the WDM device object after it has been removed, the driver can cause the system to crash.  The <a href="http://go.microsoft.com/fwlink/p/?linkid=251907">toastmon</a> sample demonstrates how the driver can provide an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function so that it is notified if the I/O target is removed.

For more information about <b>WdfIoTargetWdmGetTargetDeviceObject</b>, see <a href="https://msdn.microsoft.com/70ae920e-de2d-4014-bae4-74058b26e7c0">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.

The following code example checks an I/O target's WDM DEVICE_OBJECT structure to verify that the target supports direct I/O operations.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfiotarget.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<dl>
<dt>
<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetwdmgettargetfilehandle.md">WdfIoTargetWdmGetTargetFileHandle</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetwdmgettargetfileobject.md">WdfIoTargetWdmGetTargetFileObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetWdmGetTargetDeviceObject method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>