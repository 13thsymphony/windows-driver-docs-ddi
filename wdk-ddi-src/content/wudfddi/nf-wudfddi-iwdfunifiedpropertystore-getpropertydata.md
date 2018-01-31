---
UID : NF:wudfddi.IWDFUnifiedPropertyStore.GetPropertyData
title : IWDFUnifiedPropertyStore::GetPropertyData method
author : windows-driver-content
description : The GetPropertyData method retrieves the current setting for a device property.
old-location : wdf\iwdfunifiedpropertystore_getpropertydata.htm
old-project : wdf
ms.assetid : 0AAEB2F1-0449-4F0E-807A-1D2420CF6858
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFUnifiedPropertyStore, GetPropertyData method, IWDFUnifiedPropertyStore interface, umdf.iwdfunifiedpropertystore_getpropertydata, GetPropertyData method, IWDFUnifiedPropertyStore::GetPropertyData, wdf.iwdfunifiedpropertystore_getpropertydata, IWDFUnifiedPropertyStore interface, GetPropertyData method, GetPropertyData, wudfddi/IWDFUnifiedPropertyStore::GetPropertyData
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.11
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wudfddi.h
req.dll : WUDFx.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
---


# GetPropertyData method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetPropertyData</b> method retrieves the current setting for a device property.

## Syntax

````
HRESULT GetPropertyData(
  [in]            const DEVPROPKEY  *PropertyKey,
  [in]                  LCID        Lcid,
  [in]                  ULONG       Flags,
  [in]                  ULONG       PropertyDataSize,
  [out, optional]       PVOID       PropertyData,
  [out]                 ULONG       *PropertyDataRequiredSize,
  [out]                 DEVPROPTYPE *PropertyType
);
````

## Parameters

`PropertyKey`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a> structure that specifies the device property key.

`Lcid`

Specifies a locale identifier. Set this parameter either to a language-specific LCID value or to LOCALE_NEUTRAL. The LOCALE_NEUTRAL LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to LOCALE_SYSTEM_DEFAULT or LOCALE_USER_DEFAULT. For more information about language-specific LCID values, see <a href="http://msdn.microsoft.com/en-us/library/cc233968(PROT.10).aspx">LCID Structure</a>.

`Flags`

Reserved for system use. Drivers should set this value to 0.

`PropertyDataSize`

The size, in bytes, of the buffer that <i>PropertyData</i> points to.

`PropertyData`

A pointer to the device property data.

`PropertyDataRequiredSize`

A pointer to a ULONG to receive the size of the property information that is returned in <i>PropertyData</i>.

`PropertyType`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543546">DEVPROPTYPE</a> value. If <b>GetPropertyData</b> completes successfully, the method uses <i>PropertyType</i> to supply the type of data that is returned in the <i>PropertyData</i> buffer.


## Return Value

<b>GetPropertyData</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following values.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The framework's attempt to allocate memory failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_BUFFER_TOO_SMALL)</b></dt>
</dl>
</td>
<td width="60%">
 The <i>PropertyDataRequiredSize</i> parameter contains the size of the required buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INVALID_PARAMETER)</b></dt>
</dl>
</td>
<td width="60%">
If the driver specifies <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>, the requested interface must be one that the UMDF driver previously registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (STATUS_NOT_SUPPORTED)</b></dt>
</dl>
</td>
<td width="60%">
The driver can request device interface property data only  starting with  Windows 8.

</td>
</tr>
</table> 

This method might return one of the other values that <i>Winerror.h</i> contains.

## Remarks

Framework-based drivers use the <b>GetPropertyData</b> method to retrieve device properties that are defined as part of the unified device property model.

In particular, you can use this method to retrieve a device's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">hardware key</a> or an instance of a device interface class. When you call <a href="https://msdn.microsoft.com/A54E56A6-9A6C-435D-83FD-84BB0E072C74">IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore</a>, set the <i>RootSpecifier</i> parameter's <b>RootClass</b> member to <b>WdfPropertyStoreRootClassHardwareKey</b> or <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>.

If you specify  <b>WdfPropertyStoreRootClassHardwareKey</b>, then when you call <b>GetPropertyData</b>, you must provide a custom <a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a> value in the <i>PropertyKey</i> parameter, and  not a PnP-defined key. The value must have been previously set by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451414">SetPropertyData</a>, a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/using-device-installation-functions">SetupDI device property function</a>, or by using the <a href="https://msdn.microsoft.com/8fcb1355-f13d-4d96-aa73-62a094a52267">INF AddProperty directive</a>.

For more information about device properties, see <a href="https://msdn.microsoft.com/f41040c5-0eac-450d-b532-9165c543cc1a">Device Properties</a>.

For more information about accessing the registry, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451406">RetrieveUnifiedDevicePropertyStore</a>

<a href="..\wudfddi_types\ns-wudfddi_types-_wdf_property_store_root.md">WDF_PROPERTY_STORE_ROOT</a>

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_root_class.md">WDF_PROPERTY_STORE_ROOT_CLASS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451414">SetPropertyData</a>

<a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystorefactory.md">IWDFUnifiedPropertyStoreFactory</a>

<a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystore.md">IWDFUnifiedPropertyStore</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUnifiedPropertyStore::GetPropertyData method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>