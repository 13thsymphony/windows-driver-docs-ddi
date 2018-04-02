---
UID: NE:wudfddi_types._WDF_PNP_CAPABILITY
title: "_WDF_PNP_CAPABILITY"
author: windows-driver-content
description: The WDF_PNP_CAPABILITY enumeration contains values that identify Plug and Play (PnP) capabilities for a device.
old-location: wdf\wdf_pnp_capability.htm
old-project: wdf
ms.assetid: adcc5f64-b49c-47ca-8ef9-276537a0d7c6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_PNP_CAPABILITY, WDF_PNP_CAPABILITY enumeration, WdfPnpCapDockDevice, WdfPnpCapEjectSupported, WdfPnpCapInvalid, WdfPnpCapLockSupported, WdfPnpCapMaximum, WdfPnpCapNoDisplayInUI, WdfPnpCapRemovable, WdfPnpCapSurpriseRemovalOk, _WDF_PNP_CAPABILITY, umdf.wdf_pnp_capability, umdfstructs_365aedf9-fb60-49db-8925-bc6cf0d9a9d6.xml, wdf.wdf_pnp_capability, wudfddi_types/WDF_PNP_CAPABILITY, wudfddi_types/WdfPnpCapDockDevice, wudfddi_types/WdfPnpCapEjectSupported, wudfddi_types/WdfPnpCapInvalid, wudfddi_types/WdfPnpCapLockSupported, wudfddi_types/WdfPnpCapMaximum, wudfddi_types/WdfPnpCapNoDisplayInUI, wudfddi_types/WdfPnpCapRemovable, wudfddi_types/WdfPnpCapSurpriseRemovalOk
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi_types.h
api_name:
-	WDF_PNP_CAPABILITY
product: Windows
targetos: Windows
req.typenames: WDF_PNP_CAPABILITY
req.product: Windows 10 or later.
---

# _WDF_PNP_CAPABILITY Enumeration
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_PNP_CAPABILITY</b> enumeration contains values that identify Plug and Play (PnP) capabilities for a device.

## Syntax
```
typedef enum _WDF_PNP_CAPABILITY {
  WdfPnpCapInvalid            ,
  WdfPnpCapLockSupported      ,
  WdfPnpCapEjectSupported     ,
  WdfPnpCapRemovable          ,
  WdfPnpCapDockDevice         ,
  WdfPnpCapSurpriseRemovalOk  ,
  WdfPnpCapNoDisplayInUI      ,
  WdfPnpCapMaximum
} WDF_PNP_CAPABILITY;
```

## Constants

<table>
            
                <tr>
                    <td>WdfPnpCapInvalid</td>
                    <td>Indicates whether PnP capabilities of the device are invalid.</td>
                </tr>
            
                <tr>
                    <td>WdfPnpCapLockSupported</td>
                    <td>Indicates whether the device can be locked in its slot to prevent ejection. (Setting this capability disables ejecting a device from its slot and does not disable ejecting media from a device.)</td>
                </tr>
            
                <tr>
                    <td>WdfPnpCapEjectSupported</td>
                    <td>Indicates whether the device can be ejected from its slot. (Setting this capability enables ejecting a device from its slot and does not enable ejecting media from a device.)</td>
                </tr>
            
                <tr>
                    <td>WdfPnpCapRemovable</td>
                    <td>Indicates whether the device can be removed while the computer is running. If <b>WdfPnpCapRemovable</b> is set to <b>WdfTrue</b> and <b>WdfPnpCapSurpriseRemovalOk</b> is set to <b>WdfFalse</b>, users should use the system's Unplug or Eject Hardware application.</td>
                </tr>
            
                <tr>
                    <td>WdfPnpCapDockDevice</td>
                    <td>Indicates whether the device is a docking station.</td>
                </tr>
            
                <tr>
                    <td>WdfPnpCapSurpriseRemovalOk</td>
                    <td>Indicates whether users can remove the device without using the computer's Unplug or Eject Hardware application.</td>
                </tr>
            
                <tr>
                    <td>WdfPnpCapNoDisplayInUI</td>
                    <td>Indicates whether the device can be hidden (not displayed) in Device Manager.</td>
                </tr>
            
                <tr>
                    <td>WdfPnpCapMaximum</td>
                    <td>Valid enumeration values were exceeded.</td>
                </tr>
</table>

## Remarks

A UMDF driver supplies one of the values of <b>WDF_PNP_CAPABILITY</b> to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556974">IWDFDeviceInitialize::GetPnpCapability</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff556993">IWDFDeviceInitialize::SetPnpCapability</a> method to identify the PnP capability to retrieve or set status for.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wudfddi_types.h (include Wudfddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556974">IWDFDeviceInitialize::GetPnpCapability</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556993">IWDFDeviceInitialize::SetPnpCapability</a>