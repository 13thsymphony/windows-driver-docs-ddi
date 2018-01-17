---
UID: NF:wdfhwaccess.WDF_WRITE_REGISTER_UCHAR
title: WDF_WRITE_REGISTER_UCHAR function
author: windows-driver-content
description: The WDF_WRITE_REGISTER_UCHAR routine writes a byte to the specified address.
old-location: wdf\wdf_write_register_uchar.htm
old-project: wdf
ms.assetid: 5738654A-83B1-44B4-BA45-52E2B60C852D
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_WRITE_REGISTER_UCHAR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfhwaccess.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.alt-api: WDF_WRITE_REGISTER_UCHAR
req.alt-loc: Wdfhwaccess.h
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
req.typenames: *PWDF_FILE_INFORMATION_CLASS, WDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WDF_WRITE_REGISTER_UCHAR function



## -description
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_WRITE_REGISTER_UCHAR</b> routine writes a byte to the specified address.



## -syntax

````
void WDF_WRITE_REGISTER_UCHAR(
  _In_ WDFDEVICE Device,
  _In_ PUCHAR    Register,
  _In_ UCHAR     Value
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.


### -param Value [in]

Specifies a byte to write to the register.


## -returns
This function does not return a value.


## -remarks
