---
UID: NF.ntddk.RtlValidateCorrelationVector
title: RtlValidateCorrelationVector function
author: windows-driver-content
description: Validates the specified correlation vector to check whether it conforms to the Correlation Vector Specification (v2).
old-location: kernel\rtlvalidatecorrelationvector.htm
old-project: kernel
ms.assetid: a73ab33b-3e8c-43d8-8547-1483bcd2af52
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlValidateCorrelationVector
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
req.alt-api: RtlValidateCorrelationVector
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
---

# RtlValidateCorrelationVector function



## -description
Validates the specified correlation vector to check whether it conforms to the Correlation Vector Specification (v2).
    The function specifically checks if the first 22 bytes are a valid base64 representation of a 16 byte
        buffer
         and the remaining characters match the (\.\d+)+  regular expression.
			
            


## -syntax

````
 NTSTATUS  RtlValidateCorrelationVector(
  _Inout_ PCORRELATION_VECTOR CorrelationVector
);
````


## -parameters

### -param CorrelationVector [in, out]

A pointer to a  <a href="..\ntddk\ns-ntddk-correlation_vector.md">CORRELATION_VECTOR</a> structure that represents the correlation vector to be validated.

## -returns

Returns an NTSTATUS value that indicates the success of failure of the operation. 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The correlation vector is valid.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The supplied correlation vector is invalid.

 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10, version 1709
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddk.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe (kernel mode)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>