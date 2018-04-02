---
UID: NF:wudfddi.IWDFDeviceInitialize.RetrieveDevicePropertyStore
title: IWDFDeviceInitialize::RetrieveDevicePropertyStore method
author: windows-driver-content
description: The RetrieveDevicePropertyStore method retrieves a device property store that clients can read and write device properties through.
old-location: wdf\iwdfdeviceinitialize_retrievedevicepropertystore.htm
old-project: wdf
ms.assetid: 57d03610-b195-4691-8ee9-26c93560700c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFDeviceInitialize, IWDFDeviceInitialize interface, RetrieveDevicePropertyStore method, IWDFDeviceInitialize::RetrieveDevicePropertyStore, RetrieveDevicePropertyStore method, RetrieveDevicePropertyStore method, IWDFDeviceInitialize interface, RetrieveDevicePropertyStore,IWDFDeviceInitialize.RetrieveDevicePropertyStore, UMDFDeviceObjectRef_88af313a-0b2d-472b-b96c-549a500b0782.xml, umdf.iwdfdeviceinitialize_retrievedevicepropertystore, wdf.iwdfdeviceinitialize_retrievedevicepropertystore, wudfddi/IWDFDeviceInitialize::RetrieveDevicePropertyStore
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDeviceInitialize.RetrieveDevicePropertyStore
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFDeviceInitialize::RetrieveDevicePropertyStore method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> method retrieves a device property store that clients can read and write device properties through.

## Syntax

```
HRESULT RetrieveDevicePropertyStore(
  PCWSTR                            pcwszServiceName,
  WDF_PROPERTY_STORE_RETRIEVE_FLAGS Flags,
  IWDFNamedPropertyStore            **ppPropStore,
  WDF_PROPERTY_STORE_DISPOSITION    *pDisposition
);
```

## Parameters

`pcwszServiceName`

A pointer to a <b>NULL</b>-terminated string that represents the name of the device property store. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not supply a name for a device property store.

`Flags`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561449">WDF_PROPERTY_STORE_RETRIEVE_FLAGS</a>-typed value that identifies how to retrieve the device property store.

`ppPropStore`

A pointer to a buffer that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560164">IWDFNamedPropertyStore</a> interface that is used to retrieve device properties.

`pDisposition`

A pointer to a variable that receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561440">WDF_PROPERTY_STORE_DISPOSITION</a>-typed value that identifies whether the framework created the device property store or the device property store already existed. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the disposition information.


## Return Value

<a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

The caller should call the <b>Release</b> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560164">IWDFNamedPropertyStore</a> interface after finishing with the property store. 

For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556965">IWDFDeviceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560164">IWDFNamedPropertyStore</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561440">WDF_PROPERTY_STORE_DISPOSITION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561449">WDF_PROPERTY_STORE_RETRIEVE_FLAGS</a>