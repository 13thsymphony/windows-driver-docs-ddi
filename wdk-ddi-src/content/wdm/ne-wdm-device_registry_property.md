---
UID: NE:wdm.DEVICE_REGISTRY_PROPERTY
title: DEVICE_REGISTRY_PROPERTY
author: windows-driver-content
description: The DEVICE_REGISTRY_PROPERTY enumeration identifies device properties that are stored in the registry.
old-location: kernel\device_registry_property.htm
old-project: kernel
ms.assetid: a17b4a88-45e8-45e7-b879-2f41b97be368
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: DEVICE_REGISTRY_PROPERTY, DEVICE_REGISTRY_PROPERTY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEVICE_REGISTRY_PROPERTY
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (See Remarks section)
req.typenames: DEVICE_REGISTRY_PROPERTY
req.product: Windows 10 or later.
---

# DEVICE_REGISTRY_PROPERTY enumeration



## -description
The <b>DEVICE_REGISTRY_PROPERTY</b> enumeration identifies device properties that are stored in the registry.



## -syntax

````
typedef enum  { 
  DevicePropertyDeviceDescription            = 0x0,
  DevicePropertyHardwareID                   = 0x1,
  DevicePropertyCompatibleIDs                = 0x2,
  DevicePropertyBootConfiguration            = 0x3,
  DevicePropertyBootConfigurationTranslated  = 0x4,
  DevicePropertyClassName                    = 0x5,
  DevicePropertyClassGuid                    = 0x6,
  DevicePropertyDriverKeyName                = 0x7,
  DevicePropertyManufacturer                 = 0x8,
  DevicePropertyFriendlyName                 = 0x9,
  DevicePropertyLocationInformation          = 0xa,
  DevicePropertyPhysicalDeviceObjectName     = 0xb,
  DevicePropertyBusTypeGuid                  = 0xc,
  DevicePropertyLegacyBusType                = 0xd,
  DevicePropertyBusNumber                    = 0xe,
  DevicePropertyEnumeratorName               = 0xf,
  DevicePropertyAddress                      = 0x10,
  DevicePropertyUINumber                     = 0x11,
  DevicePropertyInstallState                 = 0x12,
  DevicePropertyRemovalPolicy                = 0x13,
  DevicePropertyResourceRequirements         = 0x14,
  DevicePropertyAllocatedResources           = 0x15,
  DevicePropertyContainerID                  = 0x16
} DEVICE_REGISTRY_PROPERTY;
````


## -enum-fields

### -field DevicePropertyDeviceDescription


### -field DevicePropertyHardwareID


### -field DevicePropertyCompatibleIDs


### -field DevicePropertyBootConfiguration


### -field DevicePropertyBootConfigurationTranslated


### -field DevicePropertyClassName


### -field DevicePropertyClassGuid


### -field DevicePropertyDriverKeyName


### -field DevicePropertyManufacturer


### -field DevicePropertyFriendlyName


### -field DevicePropertyLocationInformation


### -field DevicePropertyPhysicalDeviceObjectName


### -field DevicePropertyBusTypeGuid


### -field DevicePropertyLegacyBusType


### -field DevicePropertyBusNumber


### -field DevicePropertyEnumeratorName


### -field DevicePropertyAddress


### -field DevicePropertyUINumber


### -field DevicePropertyInstallState


### -field DevicePropertyRemovalPolicy


### -field DevicePropertyResourceRequirements


### -field DevicePropertyAllocatedResources


### -field DevicePropertyContainerID


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DEVICE_REGISTRY_PROPERTY Enumeration enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

