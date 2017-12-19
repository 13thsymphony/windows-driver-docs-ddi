---
UID: NF.wudfddi.IWDFRequestCompletionParams.GetInformation
title: IWDFRequestCompletionParams::GetInformation method
author: windows-driver-content
description: The GetInformation method retrieves information that is associated with the completion of an I/O request.
old-location: wdf\iwdfrequestcompletionparams_getinformation.htm
old-project: wdf
ms.assetid: 6dd47575-0da3-4038-81aa-ac955c00f08d
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFRequestCompletionParams, IWDFRequestCompletionParams::GetInformation, GetInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFRequestCompletionParams.GetInformation
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.product: Windows 10 or later.
---

# IWDFRequestCompletionParams::GetInformation method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInformation</b> method retrieves information that is associated with the completion of an I/O request.



## -syntax

````
ULONG_PTR GetInformation();
````


## -parameters


## -returns
<b>GetInformation</b> returns information (for example, the number of bytes transferred) that is associated with the completion of the I/O request.

For a code example of how to use the <b>GetInformation</b> method, see <a href="wdf.iwdfdevice_setpnpstate">IWDFDevice::SetPnpState</a>.

<b>GetInformation</b> returns information (for example, the number of bytes transferred) that is associated with the completion of the I/O request.

For a code example of how to use the <b>GetInformation</b> method, see <a href="wdf.iwdfdevice_setpnpstate">IWDFDevice::SetPnpState</a>.

<b>GetInformation</b> returns information (for example, the number of bytes transferred) that is associated with the completion of the I/O request.

For a code example of how to use the <b>GetInformation</b> method, see <a href="wdf.iwdfdevice_setpnpstate">IWDFDevice::SetPnpState</a>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.5

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfrequestcompletionparams.md">IWDFRequestCompletionParams</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRequestCompletionParams::GetInformation method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

