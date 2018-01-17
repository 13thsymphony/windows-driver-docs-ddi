---
UID: NF:ntddk.RtlExtendCorrelationVector
title: RtlExtendCorrelationVector function
author: windows-driver-content
description: This routine extends the supplied correlation vector. For a correlation vector of the form X.i, the extended value is X.i.0.
old-location: kernel\rtlextendcorrelationvector.htm
old-project: kernel
ms.assetid: 26de5890-edef-4e38-834a-9823327a74c2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlExtendCorrelationVector
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlExtendCorrelationVector
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode)
req.irql: PASSIVE_LEVEL
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# RtlExtendCorrelationVector function



## -description

			
            This routine extends the supplied correlation vector. For
    a correlation vector of the form X.i, the extended value is
    X.i.0.



## -syntax

````
 NTSTATUS  RtlExtendCorrelationVector(
  _Inout_ PCORRELATION_VECTOR CorrelationVector
);
````


## -parameters

### -param CorrelationVector [in, out]

A pointer to a  <a href="..\ntddk\ns-ntddk-correlation_vector.md">CORRELATION_VECTOR</a> structure that represents the correlation vector to be extended.


## -returns

Returns an NTSTATUS value that indicates the success of failure of the operation. 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The correlation vector was successfully incremented.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Extending the correlation vector resulted in
    a buffer overflow because as the extended value is no longer a valid
    correlation vector.

 


## -remarks
