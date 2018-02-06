---
UID: NF:wdfqueryinterface.WDF_QUERY_INTERFACE_CONFIG_INIT
title: WDF_QUERY_INTERFACE_CONFIG_INIT function
author: windows-driver-content
description: The WDF_QUERY_INTERFACE_CONFIG_INIT function initializes a driver's WDF_QUERY_INTERFACE_CONFIG structure.
old-location: wdf\wdf_query_interface_config_init.htm
old-project: wdf
ms.assetid: 509f4fa5-37c8-4098-aade-767aad5d6d6a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdf_query_interface_config_init, WDF_QUERY_INTERFACE_CONFIG_INIT function, WDF_QUERY_INTERFACE_CONFIG_INIT, wdfqueryinterface/WDF_QUERY_INTERFACE_CONFIG_INIT, wdf.wdf_query_interface_config_init, DFDeviceObjectDriverDefIntRef_d7e26200-d711-4c81-92d6-d2c2c1f052b0.xml
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdfqueryinterface.h
apiname:
-	WDF_QUERY_INTERFACE_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: WDF_PDO_EVENT_CALLBACKS, *PWDF_PDO_EVENT_CALLBACKS
req.product: Windows 10 or later.
---


# WDF_QUERY_INTERFACE_CONFIG_INIT function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_QUERY_INTERFACE_CONFIG_INIT</b> function initializes a driver's <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure.

## Syntax

````
VOID WDF_QUERY_INTERFACE_CONFIG_INIT(
  _Out_          PWDF_QUERY_INTERFACE_CONFIG                    InterfaceConfig,
  _In_           PINTERFACE                                     Interface,
  _In_     const GUID                                           *InterfaceType,
  _In_opt_       PFN_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST EvtDeviceProcessQueryInterfaceRequest
);
````

## Parameters

`InterfaceConfig`

A pointer to the driver's <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure.

`Interface`

A pointer to an <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure.

`InterfaceType`

A pointer to the GUID that identifies the interface.

`EvtDeviceProcessQueryInterfaceRequest`

A pointer to the driver's <a href="https://msdn.microsoft.com/b56fef85-4058-4942-90c0-36646164cd3e">EvtDeviceProcessQueryInterfaceRequest</a> event callback function, which is called when another driver requests the interface.


## Return Value

None

## Remarks

For more information about driver-defined interfaces, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfqueryinterface.h (include Wdf.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="https://msdn.microsoft.com/b56fef85-4058-4942-90c0-36646164cd3e">EvtDeviceProcessQueryInterfaceRequest</a>

<a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a>

<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_QUERY_INTERFACE_CONFIG_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>