---
UID : NE:wudfddi_types._WDF_PROPERTY_STORE_ROOT_CLASS
title : "_WDF_PROPERTY_STORE_ROOT_CLASS"
author : windows-driver-content
description : The WDF_PROPERTY_STORE_ROOT_CLASS enumeration identifies the registry keys that UMDF property stores represent.
old-location : wdf\wdf_property_store_root_class.htm
old-project : wdf
ms.assetid : f26732a7-54b5-4573-ac4f-7b2b6c8db8b0
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : "_WDF_PROPERTY_STORE_ROOT_CLASS, wudfddi_types/WdfPropertyStoreRootClassSoftwareKey, WDF_PROPERTY_STORE_ROOT_CLASS, umdfstructs_4dbaed0a-3a72-4a4c-877e-83176cce54d6.xml, wudfddi_types/WdfPropertyStoreRootClassDeviceInterfaceKey, wudfddi_types/WDF_PROPERTY_STORE_ROOT_CLASS, WdfPropertyStoreRootClassSoftwareKey, umdf.wdf_property_store_root_class, WdfPropertyStoreRootClassHardwareKey, wudfddi_types/WdfPropertyStoreRootClassLegacyHardwareKey, WDF_PROPERTY_STORE_ROOT_CLASS enumeration, wdf.wdf_property_store_root_class, wudfddi_types/WdfPropertyStoreRootClassHardwareKey, WdfPropertyStoreRootClassLegacyHardwareKey, WdfPropertyStoreRootClassDeviceInterfaceKey"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wudfddi_types.h
req.include-header : Wudfddi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.9
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_PROPERTY_STORE_ROOT_CLASS
req.product : Windows 10 or later.
---

# _WDF_PROPERTY_STORE_ROOT_CLASS Enumeration
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_PROPERTY_STORE_ROOT_CLASS</b> enumeration identifies the registry keys that UMDF property stores represent.

## Syntax
````
typedef enum _WDF_PROPERTY_STORE_ROOT_CLASS { 
  WdfPropertyStoreRootClassHardwareKey         = 0x00,
  WdfPropertyStoreRootClassSoftwareKey         = 0x01,
  WdfPropertyStoreRootClassDeviceInterfaceKey  = 0x02,
  WdfPropertyStoreRootClassLegacyHardwareKey   = 0x03
} WDF_PROPERTY_STORE_ROOT_CLASS;
````

## Constants

<table>

<tr>
<td>WdfPropertyStoreRootClassDeviceInterfaceKey</td>
<td>The property store represents the key for an instance of a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">device interface class</a>.</td>
</tr>

<tr>
<td>WdfPropertyStoreRootClassHardwareKey</td>
<td>The property store represents a device's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">hardware key</a>.</td>
</tr>

<tr>
<td>WdfPropertyStoreRootClassLegacyHardwareKey</td>
<td>The property store represents the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">DEVICEMAP key</a>, which is used by only a few older drivers.</td>
</tr>

<tr>
<td>WdfPropertyStoreRootClassSoftwareKey</td>
<td>The property store represents a driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">software key</a>.</td>
</tr>
</table>

## Remarks

The <b>WDF_PROPERTY_STORE_ROOT_CLASS</b> enumeration is used in the <a href="..\wudfddi_types\ns-wudfddi_types-_wdf_property_store_root.md">WDF_PROPERTY_STORE_ROOT</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum UMDF version** | 1.9 |
| **Header** | wudfddi_types.h (include Wudfddi.h) |

## See Also

<a href="..\wudfddi_types\ns-wudfddi_types-_wdf_property_store_root.md">WDF_PROPERTY_STORE_ROOT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_PROPERTY_STORE_ROOT_CLASS enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>