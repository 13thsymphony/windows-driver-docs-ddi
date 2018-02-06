---
UID: NS:pointofservicedriverinterface._PosMagneticStripeReaderCapabilitiesType
title: "_PosMagneticStripeReaderCapabilitiesType"
author: windows-driver-content
description: This structure defines the kinds of magnetic stripe reader (MSR) capabilities that a device supports, such as whether the device supports track data masking.
old-location: pos\posmagneticstripereadercapabilitiestype.htm
old-project: pos
ms.assetid: 8f5ad241-a145-468d-bd69-7956985152b5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PosMagneticStripeReaderCapabilitiesType, pointofservicedriverinterface/PosMagneticStripeReaderCapabilitiesType, PosMagneticStripeReaderCapabilitiesType structure, _PosMagneticStripeReaderCapabilitiesType, pos.posmagneticstripereadercapabilitiestype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	PointOfServiceDriverInterface.h
apiname:
-	PosMagneticStripeReaderCapabilitiesType
product: Windows
targetos: Windows
req.typenames: PosMagneticStripeReaderCapabilitiesType
---

# _PosMagneticStripeReaderCapabilitiesType structure
This structure defines the kinds of magnetic stripe reader (MSR) capabilities that a device supports, such as whether the device supports track data masking.

## Syntax
````
typedef struct _PosMagneticStripeReaderCapabilitiesType {
  UnifiedPosPowerReportingType            PowerReportingType;
  LONG                                    IsStatisticsReportingSupported;
  LONG                                    IsStatisticsUpdatingSupported;
  UINT32                                  CardAuthenticationLength;
  UINT32                                  SupportedEncryptionAlgorithms;
  MagneticStripeReaderAuthenticationLevel AuthenticationLevel;
  LONG                                    IsIsoSupported;
  LONG                                    IsJisOneSupported;
  LONG                                    IsJisTwoSupported;
  LONG                                    IsTrackDataMaskingSupported;
  LONG                                    IsTransmitSentinelsSupported;
} PosMagneticStripeReaderCapabilitiesType;
````

## Members


`AuthenticationLevel`

The authentication level that the device supports.

`CardAuthenticationLength`

The length, in bytes, of the name of the type of authentication that the device uses.

`IsIsoSupported`

Indicates whether the device supports ISO cards.

`IsJisOneSupported`

Indicates whether device supports JIS Type-I cards.

`IsJisTwoSupported`

Indicates whether device supports JIS Type-II cards.

`IsStatisticsReportingSupported`

Indicates whether the device supports <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_retrieve_statistics.md">IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS</a>.

`IsStatisticsUpdatingSupported`

Indicates whether the device supports <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_update_statistics.md">IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS</a>.

`IsTrackDataMaskingSupported`

Indicates whether the device is capable of masking track data.

`IsTransmitSentinelsSupported`

Indicates whether the devices is able to transmit start and end sentinels.

`PowerReportingType`

Indicates the type of power reporting that is supported by the device.

`SupportedEncryptionAlgorithms`

The supported encryption algorithm. See <a href="..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrdataencryption.md">MsrDataEncryption</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |