---
UID: NS.WDFREQUEST._WDF_REQUEST_FORWARD_OPTIONS
title: _WDF_REQUEST_FORWARD_OPTIONS
author: windows-driver-content
description: The WDF_REQUEST_FORWARD_OPTIONS structure contains options for requeuing an I/O request from a child device's I/O queue to the parent device's I/O queue.
old-location: wdf\wdf_request_forward_options.htm
old-project: wdf
ms.assetid: 61ec4a05-749d-4d60-9bd7-ad121b6fd90f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDF_REQUEST_FORWARD_OPTIONS, WDF_REQUEST_FORWARD_OPTIONS, PWDF_REQUEST_FORWARD_OPTIONS, *PWDF_REQUEST_FORWARD_OPTIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.alt-api: WDF_REQUEST_FORWARD_OPTIONS
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

# _WDF_REQUEST_FORWARD_OPTIONS structure



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_REQUEST_FORWARD_OPTIONS</b> structure contains options for requeuing an I/O request from a child device's I/O queue to the parent device's I/O queue.



## -syntax

````
typedef struct _WDF_REQUEST_FORWARD_OPTIONS {
  ULONG Size;
  ULONG Flags;
} WDF_REQUEST_FORWARD_OPTIONS, *PWDF_REQUEST_FORWARD_OPTIONS;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field Flags

A bitwise OR of <a href="wdf.wdf_request_forward_options_flags">WDF_REQUEST_FORWARD_OPTIONS_FLAGS</a>-typed flags.


## -remarks
The <b>WDF_REQUEST_FORWARD_OPTIONS</b> structure is used as input to the <a href="wdf.wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a> method.

Your driver must call <a href="wdf.wdf_request_forward_options_init">WDF_REQUEST_FORWARD_OPTIONS_INIT</a> to initialize the <b>WDF_REQUEST_FORWARD_OPTIONS</b> structure before the driver calls <a href="wdf.wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a>.


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.9

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
<a href="wdf.wdf_request_forward_options_flags">WDF_REQUEST_FORWARD_OPTIONS_FLAGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_FORWARD_OPTIONS structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

