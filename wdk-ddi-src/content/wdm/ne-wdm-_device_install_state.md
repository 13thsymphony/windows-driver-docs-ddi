---
UID: NE:wdm._DEVICE_INSTALL_STATE
title: "_DEVICE_INSTALL_STATE"
author: windows-driver-content
description: The DEVICE_INSTALL_STATE enumeration describes a device's installation state.
old-location: kernel\device_install_state.htm
old-project: kernel
ms.assetid: 82b702ae-ea62-4bc1-ad92-467eba027e3d
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PDEVICE_INSTALL_STATE, DEVICE_INSTALL_STATE, DEVICE_INSTALL_STATE enumeration [Kernel-Mode Driver Architecture], InstallStateFailedInstall, InstallStateFinishInstall, InstallStateInstalled, InstallStateNeedsReinstall, PDEVICE_INSTALL_STATE, PDEVICE_INSTALL_STATE enumeration pointer [Kernel-Mode Driver Architecture], _DEVICE_INSTALL_STATE, kernel.device_install_state, sysenum_ba359e9d-17fd-43c7-8efd-ce6c61f46be6.xml, wdm/DEVICE_INSTALL_STATE, wdm/InstallStateFailedInstall, wdm/InstallStateFinishInstall, wdm/InstallStateInstalled, wdm/InstallStateNeedsReinstall, wdm/PDEVICE_INSTALL_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	DEVICE_INSTALL_STATE
product: Windows
targetos: Windows
req.typenames: DEVICE_INSTALL_STATE, *PDEVICE_INSTALL_STATE
req.product: Windows 10 or later.
---

# _DEVICE_INSTALL_STATE Enumeration
The <b>DEVICE_INSTALL_STATE</b> enumeration describes a device's installation state.

## Syntax
````
typedef enum _DEVICE_INSTALL_STATE { 
  InstallStateInstalled       = 0,
  InstallStateNeedsReinstall  = 1,
  InstallStateFailedInstall   = 2,
  InstallStateFinishInstall   = 3
} DEVICE_INSTALL_STATE, *PDEVICE_INSTALL_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>InstallStateInstalled</td>
                    <td>The device is installed.</td>
                </tr>
            
                <tr>
                    <td>InstallStateNeedsReinstall</td>
                    <td>The system will try to reinstall the device on a later enumeration.</td>
                </tr>
            
                <tr>
                    <td>InstallStateFailedInstall</td>
                    <td>The device did not install properly.</td>
                </tr>
            
                <tr>
                    <td>InstallStateFinishInstall</td>
                    <td>The installation of this device is not yet complete.</td>
                </tr>
</table>

## Remarks

The <a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a> routine supplies a <b>DEVICE_INSTALL_STATE</b> enumeration value when a driver requests <b>DevicePropertyInstallState</b>. The operating system uses the value as a hint about the install state of the device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later versions of the Windows operating system. Available in Microsoft Windows XP and later versions of the Windows operating system. |
| **Header** | wdm.h (include Wdm.h) |

## See Also

<a href="https://msdn.microsoft.com/a17b4a88-45e8-45e7-b879-2f41b97be368">DEVICE_REGISTRY_PROPERTY</a>



<a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a>