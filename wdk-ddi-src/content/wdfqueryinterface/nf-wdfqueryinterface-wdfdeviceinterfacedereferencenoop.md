---
UID : NF:wdfqueryinterface.WdfDeviceInterfaceDereferenceNoOp
title : WdfDeviceInterfaceDereferenceNoOp function
author : windows-driver-content
description : The WdfDeviceInterfaceDereferenceNoOp method can be used for driver-defined interfaces that do not require reference counts.
old-location : wdf\wdfdeviceinterfacedereferencenoop.htm
old-project : wdf
ms.assetid : 76319a0b-a7b3-48f6-804b-e01bc360c441
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfDeviceInterfaceDereferenceNoOp
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfqueryinterface.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.alt-api : WdfDeviceInterfaceDereferenceNoOp
req.alt-loc : Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : Any level
req.typenames : WDF_PDO_EVENT_CALLBACKS, *PWDF_PDO_EVENT_CALLBACKS
req.product : Windows 10 or later.
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

You can use the <b>WdfDeviceInterfaceDereferenceNoOp</b> method's address as the <b>InterfaceDereference</b> member of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure that is contained in the framework's <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure.

For more information about interface reference counts and the <b>WdfDeviceInterfaceDereferenceNoOp</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.

For a code example that uses <b>WdfDeviceInterfaceDereferenceNoOp</b>, see <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfqueryinterface.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>
</dt>
<dt>
<a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a>
</dt>
<dt>
<a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceinterfacereferencenoop.md">WdfDeviceInterfaceReferenceNoOp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInterfaceDereferenceNoOp method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>