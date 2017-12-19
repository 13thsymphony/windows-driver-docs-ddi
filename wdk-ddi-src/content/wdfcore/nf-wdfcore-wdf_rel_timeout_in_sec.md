---
UID: NF.wdfcore.WDF_REL_TIMEOUT_IN_SEC
title: WDF_REL_TIMEOUT_IN_SEC function
author: windows-driver-content
description: The WDF_REL_TIMEOUT_IN_SEC function converts a specified number of seconds to a relative time value.
old-location: wdf\wdf_rel_timeout_in_sec.htm
old-project: wdf
ms.assetid: 40d0f5bf-609e-4609-8785-261b087fa372
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WDF_REL_TIMEOUT_IN_SEC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcore.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_REL_TIMEOUT_IN_SEC
req.alt-loc: None,None.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: Any level
req.product: Windows 10 or later.
---

# WDF_REL_TIMEOUT_IN_SEC function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REL_TIMEOUT_IN_SEC</b> function converts a specified number of seconds to a relative time value.



## -syntax

````
LONGLONG WDF_REL_TIMEOUT_IN_SEC(
  _In_ ULONGLONG Time
);
````


## -parameters

### -param Time [in]

The number of seconds to convert.


## -returns
<b>WDF_REL_TIMEOUT_IN_SEC</b> returns the relative time value, in system time units (100-nanosecond intervals), that represents the number of seconds that <i>Time</i> specifies.


## -remarks
A relative time is a time value that is relative to the current system time. For example, if a caller passes a relative time value of five seconds to a function that accepts a time-out value, the function will time out five seconds after it is called.

The following code example specifies a relative timeout value of 5 seconds for an I/O request.


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
<dt>Wdfcore.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>None</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_abs_timeout_in_sec">WDF_ABS_TIMEOUT_IN_SEC</a>
</dt>
<dt>
<a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REL_TIMEOUT_IN_SEC function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
