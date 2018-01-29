---
UID : NF:wdfresource.WdfIoResourceRequirementsListSetInterfaceType
title : WdfIoResourceRequirementsListSetInterfaceType function
author : windows-driver-content
description : The WdfIoResourceRequirementsListSetInterfaceType method assigns a bus type to a resource requirements list.
old-location : wdf\wdfioresourcerequirementslistsetinterfacetype.htm
old-project : wdf
ms.assetid : c229eb9e-cf1f-43ea-b701-fb8fb6196b40
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdfioresourcerequirementslistsetinterfacetype, kmdf.wdfioresourcerequirementslistsetinterfacetype, WdfIoResourceRequirementsListSetInterfaceType method, wdfresource/WdfIoResourceRequirementsListSetInterfaceType, PFN_WDFIORESOURCEREQUIREMENTSLISTSETINTERFACETYPE, DFResourceObjectRef_3ce545f1-cdad-4ddb-8b65-236461296d21.xml, WdfIoResourceRequirementsListSetInterfaceType
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfresource.h
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
req.irql : <=DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS"
req.product : Windows 10 or later.
---


# WdfIoResourceRequirementsListSetInterfaceType function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceRequirementsListSetInterfaceType</b> method assigns a bus type to a resource requirements list.

## Syntax

````
VOID WdfIoResourceRequirementsListSetInterfaceType(
  _In_ WDFIORESREQLIST RequirementsList,
  _In_ INTERFACE_TYPE  InterfaceType
);
````

## Parameters

`RequirementsList`

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.

`InterfaceType`

An <a href="..\wdm\ne-wdm-_interface_type.md">INTERFACE_TYPE</a>-typed value that identifies the type of bus that the device is connected to.


## Return Value

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

Your driver must provide a bus type if your device does not support Plug and Play (PnP). 

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfresource.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdm\ne-wdm-_interface_type.md">INTERFACE_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceRequirementsListSetInterfaceType method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>