---
UID: NE:ntddstor._STORAGE_COMPONENT_HEALTH_STATUS
title: "_STORAGE_COMPONENT_HEALTH_STATUS"
author: windows-driver-content
description: Indicates the health status of a storage device.
old-location: storage\storage_component_health_status.htm
old-project: storage
ms.assetid: 6768C1D7-A964-44A7-A340-98060130FF24
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSTORAGE_COMPONENT_HEALTH_STATUS, HealthStatusDisabled, HealthStatusFailed, HealthStatusNormal, HealthStatusThrottled, HealthStatusUnknown, HealthStatusWarning, PSTORAGE_COMPONENT_HEALTH_STATUS, PSTORAGE_COMPONENT_HEALTH_STATUS enumeration pointer [Storage Devices], STORAGE_COMPONENT_HEALTH_STATUS, STORAGE_COMPONENT_HEALTH_STATUS enumeration [Storage Devices], _STORAGE_COMPONENT_HEALTH_STATUS, ntddstor/HealthStatusDisabled, ntddstor/HealthStatusFailed, ntddstor/HealthStatusNormal, ntddstor/HealthStatusThrottled, ntddstor/HealthStatusUnknown, ntddstor/HealthStatusWarning, ntddstor/PSTORAGE_COMPONENT_HEALTH_STATUS, ntddstor/STORAGE_COMPONENT_HEALTH_STATUS, storage.storage_component_health_status"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	Ntddstor.h
api_name:
-	STORAGE_COMPONENT_HEALTH_STATUS
product: Windows
targetos: Windows
req.typenames: STORAGE_COMPONENT_HEALTH_STATUS, *PSTORAGE_COMPONENT_HEALTH_STATUS
---

# _STORAGE_COMPONENT_HEALTH_STATUS Enumeration
Indicates the health status of a storage device.

## Syntax
````
typedef enum _STORAGE_COMPONENT_HEALTH_STATUS { 
  HealthStatusUnknown    = 0, // 0x0
  HealthStatusNormal,
  HealthStatusThrottled,
  HealthStatusWarning,
  HealthStatusDisabled,
  HealthStatusFailed
} STORAGE_COMPONENT_HEALTH_STATUS, *PSTORAGE_COMPONENT_HEALTH_STATUS;
````

## Constants

<table>
            
                <tr>
                    <td>HealthStatusUnknown</td>
                    <td>The storage device health status is unknown.</td>
                </tr>
            
                <tr>
                    <td>HealthStatusNormal</td>
                    <td>The storage device is operating normally.</td>
                </tr>
            
                <tr>
                    <td>HealthStatusThrottled</td>
                    <td>The storage device has been throttled.</td>
                </tr>
            
                <tr>
                    <td>HealthStatusWarning</td>
                    <td>The storage device has issued a warning.</td>
                </tr>
            
                <tr>
                    <td>HealthStatusDisabled</td>
                    <td>The storage device has been disabled.</td>
                </tr>
            
                <tr>
                    <td>HealthStatusFailed</td>
                    <td>The storage device has failed.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h) |