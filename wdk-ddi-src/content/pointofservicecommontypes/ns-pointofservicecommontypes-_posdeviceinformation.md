---
UID: NS:pointofservicecommontypes._PosDeviceInformation
title: _PosDeviceInformation
author: windows-driver-content
description: This structure provides device information as defined in and required by the Unified Point of Service (UPOS) standard.
old-location: pos\posdeviceinformation.htm
old-project: pos
ms.assetid: 9ae1cfd1-1ef8-4f27-b6e1-f593bdc020e8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PosDeviceInformation, PosDeviceInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pointofservicecommontypes.h
req.include-header: PointOfServiceCommonTypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PosDeviceInformation
req.alt-loc: PointOfServiceCommonTypes.h
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
req.typenames: PosDeviceInformation
---

# _PosDeviceInformation structure



## -description
This structure provides device information as defined in and required by the Unified Point of Service (UPOS) standard.



## -syntax

````
typedef struct _PosDeviceInformation {
  wchar_t UnifiedPOSVersion[STATISTICS_STRING_SIZE];
  wchar_t DeviceCategory[STATISTICS_STRING_SIZE];
  wchar_t ManufacturerName[STATISTICS_STRING_SIZE];
  wchar_t ModelName[STATISTICS_STRING_SIZE];
  wchar_t SerialNumber[STATISTICS_STRING_SIZE];
  wchar_t ManufactureDate[STATISTICS_STRING_SIZE];
  wchar_t MechanicalRevision[STATISTICS_STRING_SIZE];
  wchar_t FirmwareRevision[STATISTICS_STRING_SIZE];
  wchar_t Interface[STATISTICS_STRING_SIZE];
  wchar_t InstallationDate[STATISTICS_STRING_SIZE];
} PosDeviceInformation;
````


## -struct-fields

### -field UnifiedPOSVersion

Indicates the version of the UPOS specification supported.


### -field DeviceCategory

Indicates the device category (for example, POSPrinter or CashDrawer).


### -field ManufacturerName

Indicates the name of the device manufacturer.


### -field ModelName

Indicates the model name of the device.


### -field SerialNumber

Indicates the serial number of the device.


### -field ManufactureDate

Indicates the date the device was manufactured.


### -field MechanicalRevision

Indicates the device hardware revision.


### -field FirmwareRevision

Indicates the device firmware revision.


### -field Interface

Indicates the device hardware interface (for example, serial or USB).


### -field InstallationDate

Indicates the device installation date.


## -remarks
These strings must be NULL terminated, and the maximum length of the strings is <code>STATISTICS_STRING_SIZE - 1</code>.</p>