---
UID: NC:wdfrequest.PFN_WDFREQUESTISFROMUSERMODEDRIVER
title: PFN_WDFREQUESTISFROMUSERMODEDRIVER function
author: windows-driver-content
description: The WdfRequestIsFromUserModeDriver method indicates whether an I/O request came from a user-mode driver or an application.
old-location: wdf\wdfrequestisfromusermodedriver.htm
old-project: wdf
ms.assetid: 2D2980D7-6675-4414-AA32-D8782526E039
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PFN_WDFREQUESTISFROMUSERMODEDRIVER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.alt-api: WdfRequestIsFromUserModeDriver
req.alt-loc: WUDFx02000.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll; TBD
req.irql: PASSIVE_LEVEL
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# PFN_WDFREQUESTISFROMUSERMODEDRIVER function



## -description
<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfRequestIsFromUserModeDriver</b> method indicates whether an I/O request came from a user-mode driver or an application.




## -syntax

````
BOOLEAN WdfRequestIsFromUserModeDriver(
  _In_ WDFREQUEST Request
);
````


## -parameters

### -param Request [in]

A handle to a framework request object.


## -returns
<b>WdfRequestIsFromUserModeDriver</b> returns <b>TRUE</b> if the specified I/O request is from a user-mode driver. The method returns <b>FALSE</b> if the current I/O request came from an application.


## -remarks
If your driver supports <a href="wdf.supporting_kernel-mode_clients_in_umdf_drivers">kernel-mode clients</a>, it should call <b>WdfRequestIsFromUserModeDriver</b> only if <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetrequestormode.md">WdfRequestGetRequestorMode</a> returns <b>WdfUserMode</b>.


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
Minimum support

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfrequest.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>WUDFx02000.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx02000.dll; </dt>
<dt>TBD</dt>
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
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetrequestormode.md">WdfRequestGetRequestorMode</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestIsFromUserModeDriver method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

