---
UID: NF:wdfiotarget.WdfIoTargetWdmGetTargetPhysicalDevice
title: WdfIoTargetWdmGetTargetPhysicalDevice function
author: windows-driver-content
description: The WdfIoTargetWdmGetTargetPhysicalDevice method returns a pointer to the Windows Driver Model (WDM) physical device object (PDO) that represents a remote I/O target's device.
old-location: wdf\wdfiotargetwdmgettargetphysicaldevice.htm
old-project: wdf
ms.assetid: ad24f1b4-ac7f-46df-8f8d-14c956c73a34
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_43beb595-b555-4253-8a54-495e9e14f071.xml, WdfIoTargetWdmGetTargetPhysicalDevice, WdfIoTargetWdmGetTargetPhysicalDevice method, kmdf.wdfiotargetwdmgettargetphysicaldevice, wdf.wdfiotargetwdmgettargetphysicaldevice, wdfiotarget/WdfIoTargetWdmGetTargetPhysicalDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfIoTargetWdmGetTargetPhysicalDevice
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---


# WdfIoTargetWdmGetTargetPhysicalDevice function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoTargetWdmGetTargetPhysicalDevice</b> method returns a pointer to the Windows Driver Model (WDM) physical device object (PDO) that represents a remote I/O target's device.

## Syntax

````
PDEVICE_OBJECT WdfIoTargetWdmGetTargetPhysicalDevice(
  _In_ WDFIOTARGET IoTarget
);
````

## Parameters

`IoTarget`

A handle to a remote I/O target object. This handle was obtained from a previous call to <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>.


## Return Value

If the I/O target represents a PnP device, <b>WdfIoTargetWdmGetTargetPhysicalDevice</b> returns a pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents a remote I/O target's PDO. Otherwise the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

The pointer that the <b>WdfIoTargetWdmGetTargetPhysicalDevice</b> method returns is valid until the driver calls <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetclose.md">WdfIoTargetClose</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcloseforqueryremove.md">WdfIoTargetCloseForQueryRemove</a>, or until the remote I/O target object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the remote I/O target object, and if the object is deleted before the remote I/O target is closed, the pointer is valid until the <i>EvtCleanupCallback</i> function returns.

If the driver attempts to access the WDM device object after it has been removed, the driver can cause the system to crash.  The <a href="http://go.microsoft.com/fwlink/p/?linkid=251907">toastmon</a> sample demonstrates how the driver can provide an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function so that it is notified if the I/O target is removed.

For more information about <b>WdfIoTargetWdmGetTargetPhysicalDevice</b>, see <a href="https://msdn.microsoft.com/70ae920e-de2d-4014-bae4-74058b26e7c0">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example obtains a pointer to a DEVICE_OBJECT structure that represents the PDO of a remote I/O target's device. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PDEVICE_OBJECT  pTargetDO;

pTargetDO = WdfIoTargetWdmGetTargetPhysicalDevice(IoTarget);</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfiotarget.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>