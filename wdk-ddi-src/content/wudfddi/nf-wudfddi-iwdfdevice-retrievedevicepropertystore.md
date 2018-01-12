---
UID: NF:wudfddi.IWDFDevice.RetrieveDevicePropertyStore
title: IWDFDevice::RetrieveDevicePropertyStore method
author: windows-driver-content
description: The RetrieveDevicePropertyStore method retrieves a property store interface that drivers can use to access the registry.
old-location: wdf\iwdfdevice_retrievedevicepropertystore.htm
old-project: wdf
ms.assetid: be47a1f0-03ff-432c-a3ef-5978c9b48183
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFDevice, IWDFDevice::RetrieveDevicePropertyStore, RetrieveDevicePropertyStore
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
req.alt-api: IWDFDevice.RetrieveDevicePropertyStore
req.alt-loc: WUDFx.dll
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
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice::RetrieveDevicePropertyStore method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveDevicePropertyStore</b> method retrieves a property store interface that drivers can use to access the registry.



## -syntax

````
HRESULT RetrieveDevicePropertyStore(
  [in, optional]  PCWSTR                            pcwszServiceName,
  [in]            WDF_PROPERTY_STORE_RETRIEVE_FLAGS Flags,
  [out]           IWDFNamedPropertyStore            **ppPropStore,
  [out, optional] WDF_PROPERTY_STORE_DISPOSITION    *pDisposition
);
````


## -parameters

### -param pcwszServiceName [in, optional]

A pointer to a <b>NULL</b>-terminated string that represents the name of the device property store. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not supply a name for a device property store. 


### -param Flags [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_retrieve_flags.md">WDF_PROPERTY_STORE_RETRIEVE_FLAGS</a>-typed value that identifies how to retrieve the device property store. 


### -param ppPropStore [out]

A pointer to a buffer that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore.md">IWDFNamedPropertyStore</a> interface. The driver uses this interface to access values in the registry.


### -param pDisposition [out, optional]

A pointer to a variable that receives a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_disposition.md">WDF_PROPERTY_STORE_DISPOSITION</a>-typed value that identifies whether the framework created the device property store or the device property store already existed. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the disposition information. 


## -returns
<b>RetrieveDevicePropertyStore</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.


## -remarks
The caller should call the <b>Release</b> method of the <a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore.md">IWDFNamedPropertyStore</a> interface after finishing with the property store. 

For more information, see <a href="wdf.using_the_registry_in_umdf_drivers">Using the Registry in UMDF-based Drivers</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.5

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore.md">IWDFNamedPropertyStore</a>
</dt>
<dt>
<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_disposition.md">WDF_PROPERTY_STORE_DISPOSITION</a>
</dt>
<dt>
<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_retrieve_flags.md">WDF_PROPERTY_STORE_RETRIEVE_FLAGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::RetrieveDevicePropertyStore method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

