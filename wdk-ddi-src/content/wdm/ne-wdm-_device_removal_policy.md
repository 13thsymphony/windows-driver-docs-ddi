---
UID: NE:wdm._DEVICE_REMOVAL_POLICY
title: "_DEVICE_REMOVAL_POLICY"
author: windows-driver-content
description: The DEVICE_REMOVAL_POLICY enumeration describes a device's removal policy.
old-location: kernel\device_removal_policy.htm
old-project: kernel
ms.assetid: 51d1f0f5-4ca1-4ea6-8561-117240551355
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: DEVICE_REMOVAL_POLICY, sysenum_46a08528-1177-4dd0-933f-6c4d7aa6c5b3.xml, RemovalPolicyExpectOrderlyRemoval, RemovalPolicyExpectNoRemoval, kernel.device_removal_policy, _DEVICE_REMOVAL_POLICY, wdm/RemovalPolicyExpectNoRemoval, RemovalPolicyExpectSurpriseRemoval, wdm/RemovalPolicyExpectSurpriseRemoval, PDEVICE_REMOVAL_POLICY enumeration pointer [Kernel-Mode Driver Architecture], PDEVICE_REMOVAL_POLICY, DEVICE_REMOVAL_POLICY enumeration [Kernel-Mode Driver Architecture], wdm/PDEVICE_REMOVAL_POLICY, wdm/RemovalPolicyExpectOrderlyRemoval, wdm/DEVICE_REMOVAL_POLICY, *PDEVICE_REMOVAL_POLICY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	DEVICE_REMOVAL_POLICY
product: Windows
targetos: Windows
req.typenames: "*PDEVICE_REMOVAL_POLICY, DEVICE_REMOVAL_POLICY"
req.product: Windows 10 or later.
---

# _DEVICE_REMOVAL_POLICY Enumeration
The <b>DEVICE_REMOVAL_POLICY</b> enumeration describes a device's removal policy.

## Syntax
````
typedef enum _DEVICE_REMOVAL_POLICY { 
  RemovalPolicyExpectNoRemoval        = 1,
  RemovalPolicyExpectOrderlyRemoval   = 2,
  RemovalPolicyExpectSurpriseRemoval  = 3
} DEVICE_REMOVAL_POLICY, *PDEVICE_REMOVAL_POLICY;
````

## Constants

<table>
            
                <tr>
                    <td>RemovalPolicyExpectNoRemoval</td>
                    <td>The device is not typically removed.</td>
                </tr>
            
                <tr>
                    <td>RemovalPolicyExpectOrderlyRemoval</td>
                    <td>The device is typically removed in an orderly fashion. (Before the device is removed, the Plug and Play [PnP] manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551705">IRP_MN_QUERY_REMOVE_DEVICE</a> request to the device's driver.)</td>
                </tr>
            
                <tr>
                    <td>RemovalPolicyExpectSurpriseRemoval</td>
                    <td>The device can be removed suddenly. (The driver receives no advance warning that the device will be removed. The Plug and Play [PnP] manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a> request when the device is removed.)</td>
                </tr>
</table>

    ## Remarks

        The <a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a> routine supplies a <b>DEVICE_REMOVAL_POLICY</b> enumeration value when a driver requests <b>DevicePropertyRemovalPolicy</b>. The operating system uses the value as a hint as to how the device is typically removed from the computer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |

    ## See Also

        <a href="https://msdn.microsoft.com/library/windows/hardware/ff551705">IRP_MN_QUERY_REMOVE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>



<a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DEVICE_REMOVAL_POLICY enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>