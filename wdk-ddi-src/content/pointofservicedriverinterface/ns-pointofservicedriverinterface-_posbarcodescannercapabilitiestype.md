---
UID : NS:pointofservicedriverinterface._PosBarcodeScannerCapabilitiesType
title : "_PosBarcodeScannerCapabilitiesType"
author : windows-driver-content
description : This structure defines the type of scanner capabilities that a device supports such as whether the device supports statistics reporting and image preview.
old-location : pos\posbarcodescannercapabilitiestype.htm
old-project : pos
ms.assetid : 4387e6f4-c980-4339-a89c-0e71c5a79e2c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PosBarcodeScannerCapabilitiesType, pointofservicedriverinterface/PosBarcodeScannerCapabilitiesType, pos.posbarcodescannercapabilitiestype, _PosBarcodeScannerCapabilitiesType, PosBarcodeScannerCapabilitiesType structure
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : pointofservicedriverinterface.h
req.include-header : PointOfServiceDriverInterface.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PosBarcodeScannerCapabilitiesType
---

# _PosBarcodeScannerCapabilitiesType structure
This structure defines the type of scanner capabilities that a device supports such as whether the device supports statistics reporting and image preview.

## Syntax
````
typedef struct _PosBarcodeScannerCapabilitiesType {
  UnifiedPosPowerReportingType PowerReportingType;
  LONG                         IsStatisticsReportingSupported;
  LONG                         IsStatisticsUpdatingSupported;
  LONG                         IsImagePreviewSupported;
} PosBarcodeScannerCapabilitiesType;
````

## Members


`IsImagePreviewSupported`

Indicates whether image data can be obtained from the barcode scanner device (in other words, whether <a href="https://msdn.microsoft.com/library/windows/hardware/dn757466">BarcodeScannerImagePreviewReceived</a> events will be sent by the driver).

`IsStatisticsReportingSupported`

Indicates whether <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_retrieve_statistics.md">IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS</a> is supported.

`IsStatisticsUpdatingSupported`

Indicates whether <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_update_statistics.md">IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS</a> is supported.

`PowerReportingType`

A <a href="..\pointofservicecommontypes\ne-pointofservicecommontypes-driverunifiedpospowerreportingtype.md">UnifiedPosPowerReportingType</a> that indicates whether the device supports standard or advanced power reporting.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |