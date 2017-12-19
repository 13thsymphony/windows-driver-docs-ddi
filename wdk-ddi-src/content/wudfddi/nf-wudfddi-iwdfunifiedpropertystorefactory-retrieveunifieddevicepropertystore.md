---
UID: NF.wudfddi.IWDFUnifiedPropertyStoreFactory.RetrieveUnifiedDevicePropertyStore
title: IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore method
author: windows-driver-content
description: The RetrieveUnifiedDevicePropertyStore method retrieves a unified property store interface.
old-location: wdf\iwdfunifiedpropertystorefactory_retrieveunifieddevicepropertystore.htm
old-project: wdf
ms.assetid: A54E56A6-9A6C-435D-83FD-84BB0E072C74
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFUnifiedPropertyStoreFactory, IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore, RetrieveUnifiedDevicePropertyStore
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IWDFUnifiedPropertyStoreFactory.RetrieveUnifiedDevicePropertyStore
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
req.product: Windows 10 or later.
---

# IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveUnifiedDevicePropertyStore</b> method retrieves a unified property store interface.



## -syntax

````
HRESULT RetrieveUnifiedDevicePropertyStore(
  [in]  PWDF_PROPERTY_STORE_ROOT RootSpecifier,
  [out] IWDFUnifiedPropertyStore **PropertyStore
);
````


## -parameters

### -param RootSpecifier [in]

The address of a driver-allocated <a href="wdf.wdf_property_store_root">WDF_PROPERTY_STORE_ROOT</a> structure. The driver fills in this structure to identify the unified property store that <b>RetrieveUnifiedDevicePropertyStore</b> retrieves.


### -param PropertyStore [out]

The address of a location that receives a pointer to an <a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystore.md">IWDFUnifiedPropertyStore</a> interface.


## -returns
<b>RetrieveUnifiedDevicePropertyStore</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The caller provided an invalid input argument.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>An attempt to allocate memory failed.

 

This method might return one of the other values that <i>Winerror.h</i> contains.


## -remarks
Your driver can call <b>RetrieveUnifiedDevicePropertyStore</b> to obtain access to a current device's hardware key or a device interface key that the device supports.

The <b>RootClass</b> member of the <a href="wdf.wdf_property_store_root">WDF_PROPERTY_STORE_ROOT</a> structure pointed to by <i>RootSpecifier</i> must be set to <b>WdfPropertyStoreRootClassHardwareKey</b> or <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>.

In addition, if <b>RootClass</b> is set to <b>WdfPropertyStoreRootClassHardwareKey</b>, then the <b>Qualifier.HardwareKey.ServiceName</b> member of <i>RootSpecifier</i> must be NULL.

For more information about accessing the registry, see <a href="wdf.using_the_registry_in_umdf_drivers">Using the Registry in UMDF-based Drivers</a>.

The following code example retrieves a unified property store interface.


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
1.11

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
<a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystorefactory.md">IWDFUnifiedPropertyStoreFactory</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystore.md">IWDFUnifiedPropertyStore</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

