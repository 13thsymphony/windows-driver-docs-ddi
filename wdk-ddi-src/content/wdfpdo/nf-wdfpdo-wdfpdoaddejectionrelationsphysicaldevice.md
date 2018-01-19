---
UID : NF:wdfpdo.WdfPdoAddEjectionRelationsPhysicalDevice
title : WdfPdoAddEjectionRelationsPhysicalDevice function
author : windows-driver-content
description : The WdfPdoAddEjectionRelationsPhysicalDevice method indicates that a specified device is ejected when another specified device is ejected.
old-location : wdf\wdfpdoaddejectionrelationsphysicaldevice.htm
old-project : wdf
ms.assetid : 23a9ab2a-be8e-40ff-8654-adf170adc6f2
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfPdoAddEjectionRelationsPhysicalDevice
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfpdo.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.alt-api : WdfPdoAddEjectionRelationsPhysicalDevice
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
req.irql : <= DISPATCH_LEVEL
req.typenames : WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product : Windows 10 or later.
---


# WdfPdoAddEjectionRelationsPhysicalDevice function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoAddEjectionRelationsPhysicalDevice</b> method indicates that a specified device is ejected when another specified device is ejected.

## Syntax

````
NTSTATUS WdfPdoAddEjectionRelationsPhysicalDevice(
  _In_ WDFDEVICE      Device,
  _In_ PDEVICE_OBJECT PhysicalDevice
);
````

## Parameters

`Device`

A handle to a framework device object.

`PhysicalDevice`

A pointer to a caller-supplied <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents a physical device object (PDO).


## Return Value

If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter is <b>NULL</b>.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A memory allocation failed.

 

The method might also return other<a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505"> NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <i>PhysicalDevice</i> parameter points to a PDO of a device that is ejected when the device that is identified by <i>Device</i> is ejected. Typically, both devices are controlled by the calling driver. Do not report the child devices of <i>Device</i> because when the PnP manager ejects a parent device, it also ejects the device's children.

For more information, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.

The following code example adds a device that the <b>pPhysicalDeviceObject</b> structure represents to the list of devices that are ejected when the device that <b>device</b> specifies is ejected.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfpdo.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<dl>
<dt>
<a href="..\wdfpdo\nf-wdfpdo-wdfpdoremoveejectionrelationsphysicaldevice.md">WdfPdoRemoveEjectionRelationsPhysicalDevice</a>
</dt>
<dt>
<a href="..\wdfpdo\nf-wdfpdo-wdfpdoclearejectionrelationsdevices.md">WdfPdoClearEjectionRelationsDevices</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoAddEjectionRelationsPhysicalDevice method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>