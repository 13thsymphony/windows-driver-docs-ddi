---
UID : NS:gnssdriver.GNSS_CWTESTDATA
title : GNSS_CWTESTDATA
author : windows-driver-content
description : This structure defines specific data elements associated with carrier wave test results returned from the driver.
old-location : sensors\gnss_cwtestdata.htm
old-project : sensors
ms.assetid : 7F1C8574-8891-4ACB-BB25-2666148E3D02
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : GNSS_CWTESTDATA, GNSS_CWTESTDATA, *PGNSS_CWTESTDATA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : gnssdriver.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : GNSS_CWTESTDATA
req.alt-loc : gnssdriver.h
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
req.typenames : GNSS_CWTESTDATA, *PGNSS_CWTESTDATA
---

# GNSS_CWTESTDATA structure
This structure defines specific data elements associated with  carrier wave test results returned from the driver.

## Syntax
````
typedef struct {
  ULONG    Size;
  ULONG    Version;
  NTSTATUS TestResultStatus;
  double   SignalToNoiseRatio;
  double   Frequency;
  BYTE     Unused[512];
} GNSS_CWTESTDATA, *PGNSS_CWTESTDATA;
````

## Members

        
            `Frequency`

            Frequency of the carrier wave detected in the measurement band.

This frequency is provided as a difference to GPS frequency (1575.42 MHz) in kHz.
        
            `SignalToNoiseRatio`

            Signal to noise ratio in the carrier wave in dB-Hz.
        
            `Size`

            Structure size.
        
            `TestResultStatus`

            NTSTATUS value indicating whether this fix contains a valid data, or if the GNSS engine or driver encountered any errors in getting the measurements for the carrier wave test.

<ul>
<li>
Success - carrier wave test successfully started.

</li>
<li>
Failed - with error code: test not implemented, carrier wave test already in progress, fix session in progress, or other failure.

</li>
</ul>
        
            `Version`

            Version number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | gnssdriver.h |