---
UID: NS.WUDFDDI_TYPES._WDF_PROPERTY_STORE_ROOT
title: _WDF_PROPERTY_STORE_ROOT
author: windows-driver-content
description: The WDF_PROPERTY_STORE_ROOT structure contains information that identifies a UMDF property store.
old-location: wdf\wdf_property_store_root.htm
old-project: wdf
ms.assetid: 431ae991-35e0-4cf7-a3e0-57591abfe5c5
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_PROPERTY_STORE_ROOT, *PWDF_PROPERTY_STORE_ROOT, WDF_PROPERTY_STORE_ROOT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: WDF_PROPERTY_STORE_ROOT
req.alt-loc: Wudfddi_types.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# _WDF_PROPERTY_STORE_ROOT structure



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]
The <b>WDF_PROPERTY_STORE_ROOT</b> structure contains information that identifies a UMDF property store. 


## -syntax

````
typedef struct _WDF_PROPERTY_STORE_ROOT {
  ULONG                         LengthCb;
  WDF_PROPERTY_STORE_ROOT_CLASS RootClass;
  union {
    struct {
      PCWSTR ServiceName;
    } HardwareKey;
    struct {
      LPCGUID InterfaceGUID;
      PCWSTR  ReferenceString;
    } DeviceInterfaceKey;
    struct {
      PCWSTR LegacyMapName;
    } LegacyHardwareKey;
  } Qualifier;
} WDF_PROPERTY_STORE_ROOT, *PWDF_PROPERTY_STORE_ROOT;
````


## -struct-fields

### -field LengthCb

The length, in bytes, of this structure.

### -field RootClass

A <a href="wdf.wdf_property_store_root_class">WDF_PROPERTY_STORE_ROOT_CLASS</a>-typed value that identifies a property store.

### -field Qualifier


### -field HardwareKey


### -field ServiceName

A pointer to a <b>NULL</b>-terminated character string that identifies a driver-specific subkey under a device's <a href="wdf.using_the_registry_in_umdf_drivers">hardware key</a> in the registry. For more information about this member, see the following Remarks section.
</dd>
</dl>

### -field DeviceInterfaceKey


### -field InterfaceGUID

A pointer to a GUID that identifies a device interface. The driver must have previously called <a href="wdf.iwdfdevice_createdeviceinterface">IWDFDevice::CreateDeviceInterface</a> to register the device interface.

### -field ReferenceString

A pointer to a <b>NULL</b>-terminated character string that identifies a reference string for a device interface. The driver must specify this member if it specified a reference string when it called <a href="wdf.iwdfdevice_createdeviceinterface">IWDFDevice::CreateDeviceInterface</a>. Otherwise, this member must be <b>NULL</b>.
</dd>
</dl>

### -field LegacyHardwareKey


### -field LegacyMapName

A pointer to a <b>NULL</b>-terminated character string that identifies a subkey under the <b>HKEY_LOCAL_MACHINE\HARDWARE\DEVICEMAP</b> key in the registry. This key is used by only a few older drivers.
</dd>
</dl>
</dd>
</dl>

## -remarks
The <b>WDF_PROPERTY_STORE_ROOT</b> structure is used as input to <a href="wdf.iwdfpropertystorefactory_retrievedevicepropertystore">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a> and <a href="wdf.iwdfunifiedpropertystorefactory_retrieveunifieddevicepropertystore">IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore</a>.

UMDF property stores represent registry keys that drivers can access. Before your driver calls one of the above methods, it must initialize the <b>WDF_PROPERTY_STORE_ROOT</b> structure. The driver must zero the structure and then set the <b>LengthCb</b> member to the structure's length.

To open a <a href="wdf.using_the_registry_in_umdf_drivers">software key</a>, your driver must:

Set the structure's <b>LengthCb</b> member to the structure size.

Set the structure's <b>RootClass</b> member to <b>WdfPropertyStoreRootClassSoftwareKey</b>.

To open a device's <a href="wdf.using_the_registry_in_umdf_drivers">hardware key</a>, your driver must:

Set the structure's <b>RootClass</b> member to <b>WdfPropertyStoreRootClassHardwareKey</b>.

Set a value for the <b>Qualifier.HardwareKey.ServiceName</b> member. This value must be one of the following:<ul>
<li>
<b>WDF_PROPERTY_STORE_HARDWARE_KEY_ROOT</b>, to open the <b>\Device Parameters</b> subkey under the device's hardware key. The driver can obtain only read access to this subkey.
</li>
<li>
<b>WDF_PROPERTY_STORE_HARDWARE_KEY_DEFAULT</b>, to open a subkey that matches the driver's service name, under the <b>\Device Parameters</b> subkey. The driver can obtain read or write access to this subkey. The driver can optionally create the subkey if it does not exist.
</li>
<li>
A driver-supplied character string, to open a subkey with a name that matches the character string, under the <b>\Device Parameters</b> subkey. The driver can obtain read or write access to this subkey. The driver can optionally create the subkey if it does not exist.
</li>
</ul>


<b>WDF_PROPERTY_STORE_HARDWARE_KEY_ROOT</b>, to open the <b>\Device Parameters</b> subkey under the device's hardware key. The driver can obtain only read access to this subkey.

<b>WDF_PROPERTY_STORE_HARDWARE_KEY_DEFAULT</b>, to open a subkey that matches the driver's service name, under the <b>\Device Parameters</b> subkey. The driver can obtain read or write access to this subkey. The driver can optionally create the subkey if it does not exist.

A driver-supplied character string, to open a subkey with a name that matches the character string, under the <b>\Device Parameters</b> subkey. The driver can obtain read or write access to this subkey. The driver can optionally create the subkey if it does not exist.

If your driver creates a subkey under a device's hardware key, it is best to specify <b>WDF_PROPERTY_STORE_HARDWARE_KEY_DEFAULT</b> because UMDF creates a subkey that matches the driver's service name. Use of this name ensures that each driver creates a uniquely named subkey. The driver must not specify WDF or WUDF as the subkey name.

To open a <a href="wdf.using_the_registry_in_umdf_drivers">device interface key</a>, your driver must:

Set the structure's <b>RootClass</b> member to <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>.

Set the <b>Qualifier.DeviceInterfaceKey.InterfaceGUID</b> member to the GUID that the driver specified to a previous call to <a href="wdf.iwdfdevice_createdeviceinterface">IWDFDevice::CreateDeviceInterface</a>.

Set the <b>Qualifier.DeviceInterfaceKey.ReferenceString</b> member to the reference string that the driver specified to a previous call to <a href="wdf.iwdfdevice_createdeviceinterface">IWDFDevice::CreateDeviceInterface</a>, or <b>NULL</b> if the driver did not specify a reference string.

The driver can obtain read or write access to the device interface key. 

To open the <a href="wdf.using_the_registry_in_umdf_drivers">DEVICEMAP key</a>, your driver must:

Set the structure's <b>RootClass</b> member to <b>WdfPropertyStoreRootClassLegacyHardwareKey</b>.

Set the <b>Qualifier.LegacyHardwareKey.LegacyMapName</b> member to a character string that specifies a subkey under the <b>HKEY_LOCAL_MACHINE\HARDWARE\DEVICEMAP</b> key in the registry.

The driver can obtain read or write access to the specified subkey under the <b>DEVICEMAP</b> key. The driver can optionally create the subkey if it does not exist. However, a driver that creates this subkey must specify the <a href="wdf.wdf_property_store_retrieve_flags">WdfPropertyStoreCreateVolatile</a> flag so that the system deletes the subkey each time that it restarts.

For more information about these registry keys, see <a href="wdf.using_the_registry_in_umdf_drivers">Using the Registry in UMDF-based Drivers</a>.

## -requirements
<table>
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
1.9
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wudfddi_types.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.iwdfpropertystorefactory_retrievedevicepropertystore">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_PROPERTY_STORE_ROOT structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
