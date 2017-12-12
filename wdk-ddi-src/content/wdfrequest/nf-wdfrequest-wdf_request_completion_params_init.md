---
UID: NF.wdfrequest.WDF_REQUEST_COMPLETION_PARAMS_INIT
title: WDF_REQUEST_COMPLETION_PARAMS_INIT function
author: windows-driver-content
description: The WDF_REQUEST_COMPLETION_PARAMS_INIT function initializes a WDF_REQUEST_COMPLETION_PARAMS structure.
old-location: wdf\wdf_request_completion_params_init.htm
old-project: wdf
ms.assetid: f13e9474-7805-4c58-983d-4cfea4f005cc
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WDF_REQUEST_COMPLETION_PARAMS_INIT
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
req.alt-api: WDF_REQUEST_COMPLETION_PARAMS_INIT
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

# WDF_REQUEST_COMPLETION_PARAMS_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b> function initializes a <a href="wdf.wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a> structure.



## -syntax

````
VOID WDF_REQUEST_COMPLETION_PARAMS_INIT(
  _Out_ PWDF_REQUEST_COMPLETION_PARAMS Params
);
````


## -parameters

### -param Params [out]

A pointer to a caller-supplied <a href="wdf.wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a> structure.


## -returns
None


## -remarks
Drivers must call <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b> to initialize a <a href="wdf.wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a> structure before calling <a href="wdf.wdfrequestgetcompletionparams">WdfRequestGetCompletionParams</a>.

The <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b> function zeros the specified <a href="wdf.wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>Type</b> member to <b>WdfRequestTypeNoFormat</b>.

For a code example that uses <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b>, see <a href="wdf.wdfrequestgetcompletionparams">WdfRequestGetCompletionParams</a>.


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
<a href="wdf.wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_COMPLETION_PARAMS_INIT function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

