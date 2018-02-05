---
UID : NS:ks.KSTIME
title : KSTIME
author : windows-driver-content
description : The KSTIME structure specifies a time stamp that can be used to indicate stream position.
old-location : stream\kstime.htm
old-project : stream
ms.assetid : e026a539-7aa5-4205-970d-cf452e4471da
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ks/PKSTIME, KSTIME, *PKSTIME, KSTIME structure [Streaming Media Devices], stream.kstime, PKSTIME structure pointer [Streaming Media Devices], ks/KSTIME, PKSTIME, ks-struct_9db70ddb-ae2c-464b-a481-6927adef449c.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
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
req.typenames : KSTIME, *PKSTIME
---

# KSTIME structure
The KSTIME structure specifies a time stamp that can be used to indicate stream position.

## Syntax
````
typedef struct {
  LONGLONG Time;
  ULONG    Numerator;
  ULONG    Denominator;
} KSTIME, *PKSTIME;
````

## Members


`Denominator`

Specifies the denominator of the scaling factor for a scaled time value. For a nonscaled value, this should be one. <b>Denominator</b> must not be zero.

`Numerator`

Specifies the numerator of the scaling factor for a scaled time value. For a nonscaled value, this should be one. <b>Numerator</b> must not be zero.

`Time`

Specifies a time value. When using unscaled time, <b>Time</b> is in units of 100-nanoseconds. When using scaled time, <b>Time</b> is in units governed by the scale factor expressed in the <b>Numerator</b> and <b>Denominator</b> members. For more information about scaled and unscaled time, see <b>Remarks</b>.

## Remarks
Unscaled time stamps are in 100-nanosecond units. A data stream can use different units by specifying the numerator and denominator of a scale factor.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |