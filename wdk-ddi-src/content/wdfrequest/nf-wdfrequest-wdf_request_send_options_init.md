---
UID: NF.wdfrequest.WDF_REQUEST_SEND_OPTIONS_INIT
title: WDF_REQUEST_SEND_OPTIONS_INIT function
author: windows-driver-content
description: The WDF_REQUEST_SEND_OPTIONS_INIT function initializes a driver's WDF_REQUEST_SEND_OPTIONS structure.
old-location: wdf\wdf_request_send_options_init.htm
old-project: wdf
ms.assetid: 65e57147-f8a1-4b9b-b856-51f89bcba149
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_REQUEST_SEND_OPTIONS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_REQUEST_SEND_OPTIONS_INIT
req.alt-loc: wdfrequest.h
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
req.product: Windows 10 or later.
---

# WDF_REQUEST_SEND_OPTIONS_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_REQUEST_SEND_OPTIONS_INIT</b> function initializes a driver's <a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.


## -syntax

````
VOID WDF_REQUEST_SEND_OPTIONS_INIT(
  _Out_ PWDF_REQUEST_SEND_OPTIONS Options,
  _In_  ULONG                     Flags
);
````


## -parameters

### -param Options [out]

A pointer to a caller-supplied <a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.

### -param Flags [in]

A bitwise OR of <a href="wdf.wdf_request_send_options_flags">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>-typed flags. 

## -returns
None

## -remarks
The <b>WDF_REQUEST_SEND_OPTIONS_INIT</b> function zeros the specified <a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure, sets the structure's <b>Size</b> member, and sets the <b>Flag</b> member to the specified <i>Flags</i> value.

The following code example initializes a <a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure and then calls <a href="wdf.wdfrequestsend">WdfRequestSend</a>.

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
Minimum KMDF version
</th>
<td width="70%">
1.0
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
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a>
</dt>
<dt>
<a href="wdf.wdf_request_send_options_flags">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>
</dt>
<dt>
<a href="wdf.wdf_request_send_options_set_timeout">WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_SEND_OPTIONS_INIT function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
