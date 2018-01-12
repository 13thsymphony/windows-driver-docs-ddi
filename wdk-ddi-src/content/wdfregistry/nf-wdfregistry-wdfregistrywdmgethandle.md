---
UID: NF:wdfregistry.WdfRegistryWdmGetHandle
title: WdfRegistryWdmGetHandle function
author: windows-driver-content
description: The WdfRegistryWdmGetHandle method returns a Windows Driver Model (WDM) handle to the registry key that a specified framework registry-key object represents.
old-location: wdf\wdfregistrywdmgethandle.htm
old-project: wdf
ms.assetid: 60638048-9009-4943-ba61-b724612852df
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WdfRegistryWdmGetHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfregistry.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfRegistryWdmGetHandle
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# WdfRegistryWdmGetHandle function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryWdmGetHandle</b> method returns a Windows Driver Model (WDM) handle to the registry key that a specified framework registry-key object represents.



## -syntax

````
HANDLE WdfRegistryWdmGetHandle(
  _In_ WDFKEY Key
);
````


## -parameters

### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


## -returns
<b>WdfRegistryWdmGetHandle</b> returns a WDM handle to a registry key. 

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
A KMDF driver can pass the returned WDM handle to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557342">ZwXxx routines</a> that accept a WDM handle as input.

A UMDF driver can pass the returned handle to APIs that require an HKEY, such as <a href="https://msdn.microsoft.com/647d34cc-01ba-4389-be29-b099ed198e7c">RegEnumKeyEx</a>.

The handle that the <b>WdfRegistryWdmGetHandle</b> method returns is valid until the registry-key object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the registry-key object, the pointer is valid until the callback function returns.

For more information about registry-key objects, see <a href="wdf.using_the_registry_in_kmdf_drivers">Using the Registry in Framework-Based Drivers</a>.

The following code example obtains a WDM handle to the registry key that a specified framework registry-key object represents.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfregistry.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>
</td>
</tr>
</table>