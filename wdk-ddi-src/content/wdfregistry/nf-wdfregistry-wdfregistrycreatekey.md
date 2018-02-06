---
UID: NF:wdfregistry.WdfRegistryCreateKey
title: WdfRegistryCreateKey function
author: windows-driver-content
description: The WdfRegistryCreateKey method creates and opens a specified registry key, or just opens the key if it already exists, and creates a framework registry-key object that represents the registry key.
old-location: wdf\wdfregistrycreatekey.htm
old-project: wdf
ms.assetid: acaf7024-b73a-4fe5-89e2-83e28cf2fdd1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdfregistrycreatekey, PFN_WDFREGISTRYCREATEKEY, WdfRegistryCreateKey method, DFRegKeyObjectRef_400650ea-7915-45f5-bcdd-2de1a02041f0.xml, wdf.wdfregistrycreatekey, wdfregistry/WdfRegistryCreateKey, WdfRegistryCreateKey
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRegistryCreateKey
product: Windows
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---


# WdfRegistryCreateKey function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryCreateKey</b> method creates and opens a specified registry key, or just opens the key if it already exists, and creates a framework registry-key object that represents the registry key.

## Syntax

````
NTSTATUS WdfRegistryCreateKey(
  _In_opt_  WDFKEY                 ParentKey,
  _In_      PCUNICODE_STRING       KeyName,
  _In_      ACCESS_MASK            DesiredAccess,
  _In_      ULONG                  CreateOptions,
  _Out_opt_ PULONG                 CreateDisposition,
  _In_opt_  PWDF_OBJECT_ATTRIBUTES KeyAttributes,
  _Out_     WDFKEY                 *Key
);
````

## Parameters

`ParentKey`

A handle to a framework registry-key object. This object represents a parent registry key that the driver has opened. This parameter is optional and can be <b>NULL</b>. If the parameter is not <b>NULL</b>, the key that <i>KeyName</i> specifies must reside under this parent key in the registry. For more information about this parent key, see the Remarks section.

`KeyName`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the name of the key to be opened. The key name can include path information. If <i>ParentKey</i> is <b>NULL</b>, <i>KeyName</i> must specify a complete path to a registry key.

`DesiredAccess`

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>-typed value that specifies access rights that the driver is requesting for the specified registry key. For a list of access rights that drivers typically use for registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558746">Opening a Handle to a Registry-Key Object</a>. Your driver must ask for only the types of access that it needs. For example, the driver must not ask for KEY_ALL_ACCESS if it will only read the registry key.

`CreateOptions`

One or more flags. For information about these flags, see the <i>CreateOptions</i> parameter or <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>.

`CreateDisposition`

A pointer to a location that receives REG_CREATED_NEW_KEY if a new key is created or REG_OPENED_EXISTING_KEY if an existing key is opened. These values are defined in <i>Wdm.h</i>. This pointer is optional and can be <b>NULL</b>.

`KeyAttributes`

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

`Key`

A pointer to a location that receives a handle to the new registry-key object.


## Return Value

<b>WdfRegistryCreateKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\wdfregistry\nf-wdfregistry-wdfregistrycreatekey.md">WdfRegistryCreateKey</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A registry-key object could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The system denied the specified access rights.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The specified registry key does not exist.

</td>
</tr>
</table> 

For a list of other return values that the <b>WdfRegistryCreateKey</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

To obtain a handle to a registry-key object that represents a parent key, your driver can call <a href="..\wdfdriver\nf-wdfdriver-wdfdriveropenparametersregistrykey.md">WdfDriverOpenParametersRegistryKey</a>, <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceopenregistrykey.md">WdfDeviceOpenRegistryKey</a>, or <a href="..\wdffdo\nf-wdffdo-wdffdoinitopenregistrykey.md">WdfFdoInitOpenRegistryKey</a>.

By default, the new registry-key object's parent is the framework driver object that the <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> method creates. You can use the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the registry-key object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the registry-key object when it has finished using the object; otherwise, the registry-key object will remain until the I/O manager unloads your driver. 

 If your driver does not change the default parent, the driver should call <a href="..\wdfregistry\nf-wdfregistry-wdfregistryclose.md">WdfRegistryClose</a> when it has finished using the object; otherwise, the registry-key object will remain until the I/O manager unloads your driver. Alternatively,  the driver can call <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a> to delete the registry-key object.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfregistry.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>

<a href="..\wdffdo\nf-wdffdo-wdffdoinitopenregistrykey.md">WdfFdoInitOpenRegistryKey</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryopenkey.md">WdfRegistryOpenKey</a>

<a href="..\wdfdriver\nf-wdfdriver-wdfdriveropenparametersregistrykey.md">WdfDriverOpenParametersRegistryKey</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceopenregistrykey.md">WdfDeviceOpenRegistryKey</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>

<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryCreateKey method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>