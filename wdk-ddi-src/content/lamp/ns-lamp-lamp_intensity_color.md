---
UID : NS:lamp.LAMP_INTENSITY_COLOR
title : LAMP_INTENSITY_COLOR
author : windows-driver-content
description : This structure is the I/O parameter type of IOCTL_LAMP_GET_INTENSITY_COLOR and IOCTL_LAMP_SET_INTENSITY_COLOR.
old-location : stream\lamp_intensity_color.htm
old-project : stream
ms.assetid : F87AFCA5-651C-4782-9F6F-C0AFB09010CB
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : LAMP_INTENSITY_COLOR, LAMP_INTENSITY_COLOR
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : lamp.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : LAMP_INTENSITY_COLOR
req.alt-loc : lamp.h
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
req.typenames : LAMP_INTENSITY_COLOR
---

# LAMP_INTENSITY_COLOR structure
This structure is the I/O parameter type of <a href="..\lamp\ni-lamp-ioctl_lamp_get_intensity_color.md">IOCTL_LAMP_GET_INTENSITY_COLOR</a> and <a href="..\lamp\ni-lamp-ioctl_lamp_set_intensity_color.md">IOCTL_LAMP_SET_INTENSITY_COLOR</a>.

## Syntax
````
typedef struct LAMP_INTENSITY_COLOR {
  BYTE Red;
  BYTE Green;
  BYTE Blue;
} LAMP_INTENSITY_COLOR;
````

## Members

        
            `Blue`

            Blue light intensity in percentage (0-100).
        
            `Green`

            Green light intensity in percentage (0-100).
        
            `Red`

            Red light intensity in percentage (0-100).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | lamp.h |