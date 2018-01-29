---
UID : NF:wdfpdo.WdfPdoRemoveEjectionRelationsPhysicalDevice
title : WdfPdoRemoveEjectionRelationsPhysicalDevice function
author : windows-driver-content
description : The WdfPdoRemoveEjectionRelationsPhysicalDevice method removes a specified device from the list of devices that must be ejected when another specified device is ejected.
old-location : wdf\wdfpdoremoveejectionrelationsphysicaldevice.htm
old-project : wdf
ms.assetid : d224b93b-4c3e-4e14-bc5d-404cb703752c
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : kmdf.wdfpdoremoveejectionrelationsphysicaldevice, PFN_WDFPDOREMOVEEJECTIONRELATIONSPHYSICALDEVICE, DFDeviceObjectFdoPdoRef_7a599cb2-dbb7-4fce-b04b-1b92638e17de.xml, wdfpdo/WdfPdoRemoveEjectionRelationsPhysicalDevice, wdf.wdfpdoremoveejectionrelationsphysicaldevice, WdfPdoRemoveEjectionRelationsPhysicalDevice method, WdfPdoRemoveEjectionRelationsPhysicalDevice
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
req.typenames : WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product : Windows 10 or later.
---


# WdfPdoRemoveEjectionRelationsPhysicalDevice function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoRemoveEjectionRelationsPhysicalDevice</b> method removes a specified device from the list of devices that must be ejected when another specified device is ejected.

## Syntax

````
VOID WdfPdoRemoveEjectionRelationsPhysicalDevice(
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

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <i>PhysicalDevice</i> parameter points to a PDO of a device that <b>WdfPdoRemoveEjectionRelationsPhysicalDevice</b> removes from the list of devices that must be ejected when the device represented by the <i>Device</i> parameter is ejected.

For more information, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.

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

<a href="..\wdfpdo\nf-wdfpdo-wdfpdoaddejectionrelationsphysicaldevice.md">WdfPdoAddEjectionRelationsPhysicalDevice</a>

<a href="..\wdfpdo\nf-wdfpdo-wdfpdoclearejectionrelationsdevices.md">WdfPdoClearEjectionRelationsDevices</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoRemoveEjectionRelationsPhysicalDevice method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>