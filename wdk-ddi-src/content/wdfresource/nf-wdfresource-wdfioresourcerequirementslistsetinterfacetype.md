---
UID: NF:wdfresource.WdfIoResourceRequirementsListSetInterfaceType
title: WdfIoResourceRequirementsListSetInterfaceType function
author: windows-driver-content
description: The WdfIoResourceRequirementsListSetInterfaceType method assigns a bus type to a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistsetinterfacetype.htm
old-project: wdf
ms.assetid: c229eb9e-cf1f-43ea-b701-fb8fb6196b40
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_3ce545f1-cdad-4ddb-8b65-236461296d21.xml, WdfIoResourceRequirementsListSetInterfaceType, WdfIoResourceRequirementsListSetInterfaceType method, kmdf.wdfioresourcerequirementslistsetinterfacetype, wdf.wdfioresourcerequirementslistsetinterfacetype, wdfresource/WdfIoResourceRequirementsListSetInterfaceType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
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
-	WdfIoResourceRequirementsListSetInterfaceType
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
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

An <a href="..\wudfwdm\ne-wudfwdm-_interface_type.md">INTERFACE_TYPE</a>-typed value that identifies the type of bus that the device is connected to.


## Return Value

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

Your driver must provide a bus type if your device does not support Plug and Play (PnP). 

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example shows how an <a href="..\wdfpdo\nc-wdfpdo-evt_wdf_device_resource_requirements_query.md">EvtDeviceResourceRequirementsQuery</a> callback function for a nonPnP device calls <b>WdfIoResourceRequirementsListSetInterfaceType</b> to assign a bus type to a device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
Example_EvtDeviceResourceRequirementsQuery(
    IN WDFDEVICE Device,
    IN WDFIORESREQLIST Requirements
    )
{
...
    WdfIoResourceRequirementsListSetInterfaceType(
                                                  Requirements,
                                                  Isa
                                                  );
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
| **Header** | wdfresource.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wudfwdm\ne-wudfwdm-_interface_type.md">INTERFACE_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceRequirementsListSetInterfaceType method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>