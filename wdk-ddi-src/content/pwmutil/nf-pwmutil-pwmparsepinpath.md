---
UID: NF.pwmutil.PwmParsePinPath
title: PwmParsePinPath function
author: windows-driver-content
description: Parses a pin path under the Pulse Width Modulation (PWM) controller namespace to validate its format and extract the pin number.
old-location: kernel\pwmparsepinpath.htm
old-project: kernel
ms.assetid: 854A2B6F-A841-4AE4-9E54-68EF048C9504
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PwmParsePinPath
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: pwmutil.h
req.include-header: Pwm.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.19
req.umdf-ver: 2.19
req.alt-api: PwmParsePinPath
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
req.irql: 
req.product: Windows 10 or later.
---

# PwmParsePinPath function



## -description
    Parses a pin path under the Pulse Width Modulation (PWM) controller namespace to validate
    its format and extract the pin number.


## -syntax

````
NTSTATUS PwmParsePinPath(
  _In_      UNICODE_STRING *PinPath,
  _Out_opt_ ULONG          *PinNumber
);
````


## -parameters

### -param PinPath [in]

A pointer to pin path as a Unicode character string.

### -param PinNumber [out, optional]

A pointer to variable that receives a pin number.

## -returns
<b>PwmParsePinPath</b> returns the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>Extracted pin path successfully from supplied pin path.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The specified pin path pointer is invalid or its Unicode string is
        invalid.
<dl>
<dt><b>STATUS_NO_SUCH_FILE</b></dt>
</dl> The specified pin path does not constitute a valid pin path.

 

## -remarks
The pin path must be a Unicode character string that ends in the pin number as follows: <i>...\&lt;PinNumber&gt;</i>.

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
Minimum KMDF version
</th>
<td width="70%">
1.19
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.19
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Pwmutil.h (include Pwm.h)</dt>
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
</table>