---
UID: NF:wdm.RtlConvertLongToLargeInteger
title: RtlConvertLongToLargeInteger function
author: windows-driver-content
description: The RtlConvertLongToLargeInteger routine converts the input signed integer to a signed large integer.
old-location: kernel\rtlconvertlongtolargeinteger.htm
old-project: kernel
ms.assetid: 8c1f6cd3-f54b-4104-bd14-63d2c284946c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlConvertLongToLargeInteger
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlConvertLongToLargeInteger
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlConvertLongToLargeInteger function



## -description
The <b>RtlConvertLongToLargeInteger</b> routine converts the input signed integer to a signed large integer.



## -syntax

````
LARGE_INTEGER RtlConvertLongToLargeInteger(
  _In_ LONG SignedInteger
);
````


## -parameters

### -param SignedInteger [in]

Specifies an integer of type LONG.


## -returns
<b>RtlConvertLongToLargeInteger</b> returns the large integer result.


## -remarks
This routine is not supported in Windows XP. Use native support for <b>__int64</b> instead. </p>