---
UID: NE:pointofservicedriverinterface._MsrErrorReportingType
title: _MsrErrorReportingType
author: windows-driver-content
description: This enumeration defines the constants that indicate the error reporting type for the magnetic stripe reader (MSR).
old-location: pos\msrerrorreportingtype.htm
old-project: pos
ms.assetid: 86b0845b-28fc-47d3-add8-dd3e8b8f631c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MsrErrorReportingType, MsrErrorReportingType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MsrErrorReportingType
req.alt-loc: pointofservicedriverinterface.h
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
req.typenames: MsrErrorReportingType
---

# _MsrErrorReportingType enumeration



## -description
This enumeration defines the constants that indicate the error reporting type for the magnetic stripe reader (MSR).



## -syntax

````
typedef enum _MsrErrorReportingType { 
  MsrErrorReportingType_CardLevel   = ,
  MsrErrorReportingType_TrackLevel
} MsrErrorReportingType;
````


## -enum-fields

### -field MsrErrorReportingType_CardLevel

Reports errors at the card level.


### -field MsrErrorReportingType_TrackLevel

Reports errors at the track level.


## -remarks
