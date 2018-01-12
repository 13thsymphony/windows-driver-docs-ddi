---
UID: NF:wudfddi.IWDFUnifiedPropertyStore.SetPropertyData
title: IWDFUnifiedPropertyStore::SetPropertyData method
author: windows-driver-content
description: The SetPropertyData method modifies the current setting of a device property.
old-location: wdf\iwdfunifiedpropertystore_setpropertydata.htm
old-project: wdf
ms.assetid: 07A79E40-6C49-4AF8-90B8-26652C46B6F1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFUnifiedPropertyStore, IWDFUnifiedPropertyStore::SetPropertyData, SetPropertyData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IWDFUnifiedPropertyStore.SetPropertyData
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

# IWDFUnifiedPropertyStore::SetPropertyData method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPropertyData</b> method modifies the current setting of a device property.



## -syntax

````
HRESULT SetPropertyData(
  [in]           const DEVPROPKEY  *PropertyKey,
  [in]                 LCID        Lcid,
  [in]                 ULONG       Flags,
  [in]                 DEVPROPTYPE PropertyType,
  [in]                 ULONG       PropertyDataSize,
  [in, optional]       PVOID       PropertyData
);
````


## -parameters

### -param PropertyKey [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a> structure that specifies the device property key.


### -param Lcid [in]

Specifies a locale identifier. Set this parameter either to a language-specific LCID value or to LOCALE_NEUTRAL. The LOCALE_NEUTRAL LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to LOCALE_SYSTEM_DEFAULT or LOCALE_USER_DEFAULT. For more information about language-specific LCID values, see <a href="http://msdn.microsoft.com/en-us/library/cc233968(PROT.10).aspx">LCID Structure</a>.


### -param Flags [in]

Reserved. Drivers should set this value to 0.


### -param PropertyType [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543546">DEVPROPTYPE</a> value that specifies the type of the data that is provided in the <i>PropertyData</i> buffer.


### -param PropertyDataSize [in]

The size, in bytes, of the buffer that <i>PropertyData</i> points to.


### -param PropertyData [in, optional]

A pointer to the device property data. Set this parameter to <b>NULL</b> to delete the specified property.


## -returns
<b>SetPropertyData</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following values.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>The framework's attempt to allocate memory failed.
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INVALID_PARAMETER)</b></dt>
</dl>If the driver specifies <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>, the requested interface must be one that the UMDF driver previously registered.
<dl>
<dt><b>HRESULT_FROM_WIN32 (STATUS_NOT_SUPPORTED)</b></dt>
</dl>The driver can modify device interface property data only  starting with  Windows 8.

 

This method might return an HRESULT-typed value corresponding to one of the other values that <i>Winerror.h</i> contains.


## -remarks
Framework-based drivers use the <b>SetPropertyData</b> method to modify device properties that are defined as part of the unified device property model.

In particular, you can use this method to modify a device's <a href="wdf.using_the_registry_in_umdf_drivers">hardware key</a> or an instance of a device interface class. When you call <a href="https://msdn.microsoft.com/A54E56A6-9A6C-435D-83FD-84BB0E072C74">IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore</a>, set the <i>RootSpecifier</i> parameter's <b>RootClass</b> member to <b>WdfPropertyStoreRootClassHardwareKey</b> or <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>.  

If you specify  <b>WdfPropertyStoreRootClassHardwareKey</b>, then when you call <b>SetPropertyData</b>, you must provide a custom <a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a> value in the <i>PropertyKey</i> parameter, and  not a PnP-defined key. The value must have been previously set by calling <b>SetPropertyData</b>, a <a href="devinst.using_device_installation_functions#ddk_setupdi_device_property_functions_dg#ddk_setupdi_device_property_functions_dg">SetupDI device property function</a>, or by using the <a href="https://msdn.microsoft.com/8fcb1355-f13d-4d96-aa73-62a094a52267">INF AddProperty directive</a>.

If the driver specifies <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>, the requested interface must be one that the UMDF driver previously registered at runtime.


If the driver registers an interface in its INF file, it must set associated properties in the INF as well.

For more information about accessing the registry, see <a href="wdf.using_the_registry_in_umdf_drivers">Using the Registry in UMDF-based Drivers</a>.


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
<dt>Wudfddi.h</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451406">RetrieveUnifiedDevicePropertyStore</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystore.md">IWDFUnifiedPropertyStore</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451410">GetPropertyData</a>
</dt>
<dt>
<a href="..\wudfddi_types\ns-wudfddi_types-_wdf_property_store_root.md">WDF_PROPERTY_STORE_ROOT</a>
</dt>
<dt>
<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_root_class.md">WDF_PROPERTY_STORE_ROOT_CLASS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUnifiedPropertyStore::SetPropertyData method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

