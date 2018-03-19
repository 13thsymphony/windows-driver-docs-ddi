---
UID: NF:wdfiotarget.WdfIoTargetGetDevice
title: WdfIoTargetGetDevice function
author: windows-driver-content
description: The WdfIoTargetGetDevice method returns a handle to the framework device object that is the parent of the specified local or remote I/O target.
old-location: wdf\wdfiotargetgetdevice.htm
old-project: wdf
ms.assetid: 2e076f2f-59e3-43ca-b83e-3079bbf41df3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_796e5254-23b4-4ed1-b02b-66c5c8560769.xml, WdfIoTargetGetDevice, WdfIoTargetGetDevice method, kmdf.wdfiotargetgetdevice, wdf.wdfiotargetgetdevice, wdfiotarget/WdfIoTargetGetDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
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
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfIoTargetGetDevice
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---


# WdfIoTargetGetDevice function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetGetDevice</b> method returns a handle to the framework device object that is the parent of the specified local or remote I/O target.

## Syntax

````
WDFDEVICE WdfIoTargetGetDevice(
  _In_ WDFIOTARGET IoTarget
);
````

## Parameters

`IoTarget`

A handle to an I/O target object. This handle is obtained from <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>, <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>, or from a method that a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/introduction-to-i-o-targets">specialized I/O target</a> supplies (such as <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetiotarget.md">WdfUsbTargetDeviceGetIoTarget</a>).


## Return Value

<b>WdfIoTargetGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about <b>WdfIoTargetGetDevice</b>, see <a href="https://msdn.microsoft.com/70ae920e-de2d-4014-bae4-74058b26e7c0">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example is shows how an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function can call <b>WdfIoTargetGetDevice</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
MyEvtIoTargetQueryRemove(
    WDFIOTARGET IoTarget
)
{
WDFDEVICE device;
...
device = WdfIoTargetGetDevice(IoTarget);
...
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfiotarget.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetiotarget.md">WdfUsbTargetDeviceGetIoTarget</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>