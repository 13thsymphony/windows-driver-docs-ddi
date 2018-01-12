---
UID: NF:spbcx.SpbRequestGetParameters
title: SpbRequestGetParameters function
author: windows-driver-content
description: The SpbRequestGetParameters method retrieves a set of SPB-specific parameter values from an I/O request.
old-location: spb\spbrequestgetparameters.htm
old-project: SPB
ms.assetid: 676C28C4-E6F3-4190-927B-67D5618F5645
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SpbRequestGetParameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SpbRequestGetParameters
req.alt-loc: spbcxstubs.lib,spbcxstubs.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Spbcxstubs.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: *PSPB_REQUEST_TYPE, SPB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# SpbRequestGetParameters function



## -description
The <b>SpbRequestGetParameters</b> method retrieves a set of SPB-specific parameter values from an I/O request.



## -syntax

````
VOID SpbRequestGetParameters(
  _In_  SPBREQUEST             SpbRequest,
  _Out_ SPB_REQUEST_PARAMETERS *Parameters
);
````


## -parameters

### -param SpbRequest [in]

An <a href="buses.spbrequest_object_handle">SPBREQUEST</a>  handle to the I/O request. The SPB controller driver previously received this handle through one of its registered <a href="https://msdn.microsoft.com/1DA1FF41-FB01-45CC-B0C1-EAF2C81D0CDA">event callback functions</a>.


### -param Parameters [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/91A5C504-7072-4B64-86F1-2BDE616CCA31">SPB_REQUEST_PARAMETERS</a> structure into which the method writes the SPB-specific parameter values from the I/O request. The caller must have previously initialized this structure by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406210">SPB_REQUEST_PARAMETERS_INIT</a> function.


## -returns
None.


## -remarks
<b>SpbRequestGetParameters</b> is similar to the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a> method, but retrieves only SPB-specific information. Your SPB controller driver can call  <b>SpbRequestGetParameters</b> to retrieve SPB-specific information from I/O requests that it receives from the SPB framework extension (SpbCx). The SPB controller driver can call <b>WdfRequestGetParameters</b> to retrieve the generic request parameters from I/O requests that it receives.

The following code example shows how to use <b>SpbRequestGetParameters</b> to retrieve the SPB-specific parameters from an I/O request. The  <i>spbRequest</i> variable contains an SPBREQUEST handle to the I/O request.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Spbcx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Spbcxstubs.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.spbrequest_object_handle">SPBREQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/91A5C504-7072-4B64-86F1-2BDE616CCA31">SPB_REQUEST_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406210">SPB_REQUEST_PARAMETERS_INIT</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SpbRequestGetParameters method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

