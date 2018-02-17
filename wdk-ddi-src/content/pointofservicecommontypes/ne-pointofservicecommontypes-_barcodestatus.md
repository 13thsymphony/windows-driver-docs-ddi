---
UID: NE:pointofservicecommontypes._BarcodeStatus
title: "_BarcodeStatus"
author: windows-driver-content
description: This enumeration indicates barcode scanner status values.
old-location: pos\barcodestatus.htm
old-project: pos
ms.assetid: b89ee18b-229d-4ec7-8c69-1b75ad0f3448
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: BarcodeStatusUpdateType_Off, _BarcodeStatus, pointofservicecommontypes/BarcodeStatusUpdateType_Extended, pointofservicecommontypes/BarcodeStatusUpdateType_Online, pointofservicecommontypes/BarcodeStatusUpdateType_Off, pointofservicecommontypes/BarcodeStatusUpdateType_OffOrOffline, pointofservicecommontypes/BarcodeStatusUpdateType_Offline, pointofservicecommontypes/BarcodeStatus, BarcodeStatusUpdateType_OffOrOffline, BarcodeStatusUpdateType_Extended, BarcodeStatusUpdateType_Online, BarcodeStatusUpdateType_Offline, BarcodeStatus enumeration, pos.barcodestatus, BarcodeStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pointofservicecommontypes.h
req.include-header: Pointofservicecommontypes.h
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
-	pointofservicecommontypes.h
apiname:
-	BarcodeStatus
product: Windows
targetos: Windows
req.typenames: BarcodeStatus
---

# _BarcodeStatus Enumeration
This enumeration indicates barcode scanner status values.

## Syntax
````
typedef enum _BarcodeStatus { 
  BarcodeStatusUpdateType_Online        = 0,
  BarcodeStatusUpdateType_Off           = 1,
  BarcodeStatusUpdateType_Offline       = 2,
  BarcodeStatusUpdateType_OffOrOffline  = 3,
  BarcodeStatusUpdateType_Extended      = 4
} BarcodeStatus;
````

## Constants

<table>
            
                <tr>
                    <td>BarcodeStatusUpdateType_Extended</td>
                    <td>Vendor specific status information.</td>
                </tr>
            
                <tr>
                    <td>BarcodeStatusUpdateType_Off</td>
                    <td>The device power is off or detached from the terminal. This is valid if <a href="..\pointofservicecommontypes\ne-pointofservicecommontypes-driverunifiedpospowerreportingtype.md">UnifiedPosPowerReportingType</a> is <b>Advanced</b>.</td>
                </tr>
            
                <tr>
                    <td>BarcodeStatusUpdateType_Offline</td>
                    <td>The device power is on, but it is not ready or unable to respond to requests. This is valid if <a href="..\pointofservicecommontypes\ne-pointofservicecommontypes-driverunifiedpospowerreportingtype.md">UnifiedPosPowerReportingType</a> is <b>Advanced</b>.</td>
                </tr>
            
                <tr>
                    <td>BarcodeStatusUpdateType_OffOrOffline</td>
                    <td>The device power is off or the device is offline. This is valid if <a href="..\pointofservicecommontypes\ne-pointofservicecommontypes-driverunifiedpospowerreportingtype.md">UnifiedPosPowerReportingType</a> is <b>Standard</b>.</td>
                </tr>
            
                <tr>
                    <td>BarcodeStatusUpdateType_Online</td>
                    <td>The device is online. This is valid if <a href="..\pointofservicecommontypes\ne-pointofservicecommontypes-driverunifiedpospowerreportingtype.md">UnifiedPosPowerReportingType</a> is <b>Standard</b> or <b>Advanced</b>.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicecommontypes.h (include Pointofservicecommontypes.h) |