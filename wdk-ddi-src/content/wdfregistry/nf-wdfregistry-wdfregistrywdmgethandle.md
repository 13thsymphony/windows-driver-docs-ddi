---
UID : NF:wdfregistry.WdfRegistryWdmGetHandle
title : WdfRegistryWdmGetHandle function
author : windows-driver-content
description : The WdfRegistryWdmGetHandle method returns a Windows Driver Model (WDM) handle to the registry key that a specified framework registry-key object represents.
old-location : wdf\wdfregistrywdmgethandle.htm
old-project : wdf
ms.assetid : 60638048-9009-4943-ba61-b724612852df
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfRegistryWdmGetHandle, DFRegKeyObjectRef_9229cd7b-fb26-4e95-a5ee-5deb31f549f4.xml, WdfRegistryWdmGetHandle method, wdf.wdfregistrywdmgethandle, kmdf.wdfregistrywdmgethandle, wdfregistry/WdfRegistryWdmGetHandle
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfregistry.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : DriverCreate
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_QUERY_INTERFACE_CONFIG, WDF_QUERY_INTERFACE_CONFIG"
req.product : Windows 10 or later.
---


# WdfRegistryWdmGetHandle function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryWdmGetHandle</b> method returns a Windows Driver Model (WDM) handle to the registry key that a specified framework registry-key object represents.

## Syntax

````
HANDLE WdfRegistryWdmGetHandle(
  _In_ WDFKEY Key
);
````

## Parameters

`Key`

A handle to a registry-key object that represents an opened registry key.


## Return Value

<b>WdfRegistryWdmGetHandle</b> returns a WDM handle to a registry key. 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

A KMDF driver can pass the returned WDM handle to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557342">ZwXxx routines</a> that accept a WDM handle as input.

A UMDF driver can pass the returned handle to APIs that require an HKEY, such as <a href="https://msdn.microsoft.com/647d34cc-01ba-4389-be29-b099ed198e7c">RegEnumKeyEx</a>.

The handle that the <b>WdfRegistryWdmGetHandle</b> method returns is valid until the registry-key object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the registry-key object, the pointer is valid until the callback function returns.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfregistry.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate |