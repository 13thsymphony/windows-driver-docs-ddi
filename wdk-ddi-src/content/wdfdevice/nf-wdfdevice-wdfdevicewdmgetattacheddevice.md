---
UID : NF:wdfdevice.WdfDeviceWdmGetAttachedDevice
title : WdfDeviceWdmGetAttachedDevice function
author : windows-driver-content
description : The WdfDeviceWdmGetAttachedDevice method returns the next-lower WDM device object in the device stack.
old-location : wdf\wdfdevicewdmgetattacheddevice.htm
old-project : wdf
ms.assetid : 216fe649-18c0-4782-8040-21ce87fbd888
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfDeviceWdmGetAttachedDevice method, wdfdevice/WdfDeviceWdmGetAttachedDevice, kmdf.wdfdevicewdmgetattacheddevice, WdfDeviceWdmGetAttachedDevice, PFN_WDFDEVICEWDMGETATTACHEDDEVICE, DFDeviceObjectGeneralRef_cfd9610b-28f6-4c5c-a532-9c5fae3576fc.xml, wdf.wdfdevicewdmgetattacheddevice
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfdevice.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_STATE_NOTIFICATION_TYPE
req.product : Windows 10 or later.
---


# WdfDeviceWdmGetAttachedDevice function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceWdmGetAttachedDevice</b> method returns the next-lower WDM device object in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/wdm-concepts-for-kmdf-drivers">device stack</a>.

## Syntax

````
PDEVICE_OBJECT WdfDeviceWdmGetAttachedDevice(
  _In_ WDFDEVICE Device
);
````

## Parameters

`Device`

A handle to a framework device object.


## Return Value

<b>WdfDeviceWdmGetAttachedDevice</b> returns a pointer to a WDM <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. If the specified object handle represents a physical device object (PDO), the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

The pointer that the <b>WdfDeviceWdmGetAttachedDevice</b> method returns is valid until the framework device object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the framework device object, the pointer is valid until the callback function returns.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmgetphysicaldevice.md">WdfDeviceWdmGetPhysicalDevice</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmgetdeviceobject.md">WdfDeviceWdmGetDeviceObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceWdmGetAttachedDevice method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>