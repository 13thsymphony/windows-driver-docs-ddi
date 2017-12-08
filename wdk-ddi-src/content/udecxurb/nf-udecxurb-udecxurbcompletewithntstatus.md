---
UID: NF.udecxurb.UdecxUrbCompleteWithNtStatus
title: UdecxUrbCompleteWithNtStatus function
author: windows-driver-content
description: Completes the URB request with an NTSTATUS code.
old-location: buses\udecxurbcompletewithntstatus.htm
old-project: usbref
ms.assetid: E1EAA11F-B32F-4551-9788-49BC8A13BB19
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UdecxUrbCompleteWithNtStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxurb.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.alt-api: UdecxUrbCompleteWithNtStatus
req.alt-loc: Udecxstub.lib,Udecxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# UdecxUrbCompleteWithNtStatus function



## -description
Completes the URB request with an <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.



## -syntax

````
FORCEINLINE void UdecxUrbCompleteWithNtStatus(
  _In_ WDFREQUEST Request,
  _In_ NTSTATUS   NtStatus
);
````


## -parameters

### -param Request [in]

A handle to a framework request object that contains the <a href="buses.urb">URB</a> for the transfer.

### -param NtStatus [in]

A <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a>-typed value that indicates the success or failure of the completed URB request. 

## -returns
This function does not return a value.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
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
1.15
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>UdecxUrb.h (include Udecx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Udecxstub.lib</dt>
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

## -see-also
<dl>
<dt>
<a href="buses.usb_emulated_device__ude__architecture">Architecture: USB Device Emulation (UDE)</a>
</dt>
<dt>
<a href="buses.writing_a_ude_client_driver">Write a UDE client driver</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUrbCompleteWithNtStatus function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
