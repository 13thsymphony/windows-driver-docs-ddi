---
UID: NF:wdfregistry.WdfRegistryRemoveKey
title: WdfRegistryRemoveKey function
author: windows-driver-content
description: The WdfRegistryRemoveKey method removes the registry key that is associated with a specified framework registry-key object and then deletes the registry-key object.
old-location: wdf\wdfregistryremovekey.htm
old-project: wdf
ms.assetid: b23d1c2f-15f0-4b9e-8a10-9b81056fa509
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRegistryRemoveKey
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
req.alt-api: WdfRegistryRemoveKey
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_QUERY_INTERFACE_CONFIG, WDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# WdfRegistryRemoveKey function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryRemoveKey</b> method removes the registry key that is associated with a specified framework registry-key object and then deletes the registry-key object.



## -syntax

````
NTSTATUS WdfRegistryRemoveKey(
  _In_ WDFKEY Key
);
````


## -parameters

### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


## -returns
<b>WdfRegistryRemoveKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
<a href="..\wdfregistry\nf-wdfregistry-wdfregistryremovekey.md">WdfRegistryRemoveKey</a> was not called at IRQL = PASSIVE_LEVEL. 
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The driver did not open the registry key with deletion access.
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>See the Remarks section.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
<p class="note">From a KMDF driver, do not call <b>WdfRegistryRemoveKey</b> and then <a href="..\wdfregistry\nf-wdfregistry-wdfregistryclose.md">WdfRegistryClose</a> on the same key. The WDFKEY is no longer valid after <b>WdfRegistryRemoveKey</b> returns.

While it is legal for a UMDF driver to call <b>WdfRegistryRemoveKey</b>, the call always returns <b>STATUS_NOT_IMPLEMENTED</b>.   To delete the WDFKEY object, a UMDF driver should instead call <a href="..\wdfregistry\nf-wdfregistry-wdfregistryclose.md">WdfRegistryClose</a>.

<b>WdfRegistryRemoveKey</b> does not return STATUS_SUCCESS if the specified key object represents a registry key that has subkeys. In other words, the driver must remove the subkeys first.

For more information about registry-key objects, see <a href="wdf.using_the_registry_in_kmdf_drivers">Using the Registry in Framework-Based Drivers</a>.

The following code example removes a registry key and deletes the registry-key object.</p>