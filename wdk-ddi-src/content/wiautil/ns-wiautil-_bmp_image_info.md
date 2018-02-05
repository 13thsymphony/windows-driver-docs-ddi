---
UID : NS:wiautil._BMP_IMAGE_INFO
title : "_BMP_IMAGE_INFO"
author : windows-driver-content
description : The BMP_IMAGE_INFO structure contains information about a BMP image.
old-location : image\bmp_image_info.htm
old-project : image
ms.assetid : 953e2f00-2275-49a2-b1e5-def7763a8ab7
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*PBMP_IMAGE_INFO, wiauFncs_b4043c8e-769f-4ab1-9d62-c96dd5d7b487.xml, BMP_IMAGE_INFO, PBMP_IMAGE_INFO, wiautil/PBMP_IMAGE_INFO, _BMP_IMAGE_INFO, BMP_IMAGE_INFO structure [Imaging Devices], PBMP_IMAGE_INFO structure pointer [Imaging Devices], image.bmp_image_info, wiautil/BMP_IMAGE_INFO"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wiautil.h
req.include-header : Wiautil.h, Wiamindr.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows XP and later.
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
req.typenames : BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product : Windows 10 or later.
---

# _BMP_IMAGE_INFO structure
The BMP_IMAGE_INFO structure contains information about a BMP image.

## Syntax
````
typedef struct _BMP_IMAGE_INFO {
  INT Width;
  INT Height;
  INT ByteWidth;
  INT Size;
} BMP_IMAGE_INFO, *PBMP_IMAGE_INFO;
````

## Members


`ByteWidth`

Specifies the width of the image, in bytes.

`Height`

Specifies the height of the image, in lines.

`Size`

Specifies the total size of the image, including headers, in bytes.

`Width`

Specifies the width of the image, in pixels.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later. Available in Windows XP and later. |
| **Header** | wiautil.h (include Wiautil.h, Wiamindr.h) |