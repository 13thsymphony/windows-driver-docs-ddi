---
UID : NF:wdfpdo.WdfPdoClearEjectionRelationsDevices
title : WdfPdoClearEjectionRelationsDevices function
author : windows-driver-content
description : The WdfPdoClearEjectionRelationsDevices method removes all devices from the list of devices that must be ejected when a specified device is ejected.
old-location : wdf\wdfpdoclearejectionrelationsdevices.htm
old-project : wdf
ms.assetid : 09154884-130d-47aa-be00-08a3a4da6f22
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfPdoClearEjectionRelationsDevices
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
req.alt-api : WdfPdoClearEjectionRelationsDevices
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


# WdfPdoClearEjectionRelationsDevices function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoClearEjectionRelationsDevices</b> method removes all devices from the list of devices that must be ejected when a specified device is ejected.

## Syntax

````
VOID WdfPdoClearEjectionRelationsDevices(
  _In_ WDFDEVICE Device
);
````

## Parameters

`Device`

A handle to a framework device object.


## Return Value

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.

The following code example clears the specified device's list of ejection relations.

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
<a href="..\wdfpdo\nf-wdfpdo-wdfpdoaddejectionrelationsphysicaldevice.md">WdfPdoAddEjectionRelationsPhysicalDevice</a>
</dt>
<dt>
<a href="..\wdfpdo\nf-wdfpdo-wdfpdoremoveejectionrelationsphysicaldevice.md">WdfPdoRemoveEjectionRelationsPhysicalDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoClearEjectionRelationsDevices method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>