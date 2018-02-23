---
UID: NF:wdfqueryinterface.WdfDeviceInterfaceDereferenceNoOp
title: WdfDeviceInterfaceDereferenceNoOp function
author: windows-driver-content
description: The WdfDeviceInterfaceDereferenceNoOp method can be used for driver-defined interfaces that do not require reference counts.
old-location: wdf\wdfdeviceinterfacedereferencenoop.htm
old-project: wdf
ms.assetid: 76319a0b-a7b3-48f6-804b-e01bc360c441
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfDeviceInterfaceDereferenceNoOp method, WdfDeviceInterfaceDereferenceNoOp, DFDeviceObjectDriverDefIntRef_2bfa96a8-a58a-4408-83db-11670d7de8c7.xml, wdfqueryinterface/WdfDeviceInterfaceDereferenceNoOp, kmdf.wdfdeviceinterfacedereferencenoop, wdf.wdfdeviceinterfacedereferencenoop
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfqueryinterface.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceInterfaceDereferenceNoOp
product: Windows
targetos: Windows
req.typenames: "*PWDF_PDO_EVENT_CALLBACKS, WDF_PDO_EVENT_CALLBACKS"
req.product: Windows 10 or later.
---


# WdfDeviceInterfaceDereferenceNoOp function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInterfaceDereferenceNoOp</b> method can be used for driver-defined interfaces that do not require reference counts.

## Syntax

````
VOID WdfDeviceInterfaceDereferenceNoOp(
  _In_ PVOID Context
);
````

## Parameters

`Context`

This parameter is not used.


## Return Value

None

## Remarks

You can use the <b>WdfDeviceInterfaceDereferenceNoOp</b> method's address as the <b>InterfaceDereference</b> member of the <a href="..\miniport\ns-miniport-_interface.md">INTERFACE</a> structure that is contained in the framework's <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure.

For more information about interface reference counts and the <b>WdfDeviceInterfaceDereferenceNoOp</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


#### Examples

For a code example that uses <b>WdfDeviceInterfaceDereferenceNoOp</b>, see <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfqueryinterface.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | Any level |

## See Also

<a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a>



<a href="..\miniport\ns-miniport-_interface.md">INTERFACE</a>



<a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceinterfacereferencenoop.md">WdfDeviceInterfaceReferenceNoOp</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInterfaceDereferenceNoOp method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>