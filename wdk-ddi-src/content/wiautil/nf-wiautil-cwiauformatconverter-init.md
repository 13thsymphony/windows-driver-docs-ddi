---
UID: NF:wiautil.CWiauFormatConverter.Init
title: CWiauFormatConverter::Init method
author: windows-driver-content
description: The CWiauFormatConverter::Init method initializes the CWiauFormatConverter class and GDI+ for converting images. This method should be called only once.
old-location: image\cwiauformatconverter_init.htm
old-project: image
ms.assetid: 342ea1ae-ff8c-429d-bee8-08559fe75b40
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: CWiauFormatConverter, CWiauFormatConverter interface [Imaging Devices], Init method, CWiauFormatConverter::Init, Init method [Imaging Devices], Init method [Imaging Devices], CWiauFormatConverter interface, Init,CWiauFormatConverter.Init, image.cwiauformatconverter_init, wiauFncs_d762c597-47d1-446a-b76d-7993ba32f571.xml, wiautil/CWiauFormatConverter::Init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
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
-	COM
api_location:
-	Wiautil.h
api_name:
-	CWiauFormatConverter.Init
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# Init method
The <b>CWiauFormatConverter::Init</b> method initializes the <b>CWiauFormatConverter</b> class and GDI+ for converting images. This method should be called only once.

## Syntax

````
HRESULT Init();
````

## Parameters

This function has no parameters.

## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h, Wiamindr.h) |