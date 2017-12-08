---
UID: NF.wudfddi.IWDFIoRequest2.GetSetInformationParameters
title: IWDFIoRequest2::GetSetInformationParameters
author: windows-driver-content
description: The GetSetInformationParameters method retrieves parameters that are associated with a WdfRequestSetInformation-typed I/O request.
old-location: wdf\iwdfiorequest2_getsetinformationparameters.htm
old-project: wdf
ms.assetid: 44872d92-4a71-4cc7-9f7c-c95477ac3264
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IWDFIoRequest2, GetSetInformationParameters, IWDFIoRequest2::GetSetInformationParameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFIoRequest2.GetSetInformationParameters
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
req.irql: <= DISPATCH_LEVEL
req.iface: IWDFIoRequest2
req.product: Windows 10 or later.
---

# IWDFIoRequest2::GetSetInformationParameters method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>GetSetInformationParameters</b> method retrieves parameters that are associated with a <a href="..\wudfddi_types\ne-wudfddi-types--wdf-request-type.md">WdfRequestSetInformation</a>-typed I/O request.</p>


## -syntax

````
void GetSetInformationParameters(
  [out, optional] WDF_FILE_INFORMATION_CLASS *pInformationClass,
  [out, optional] SIZE_T                     *pSizeInBytes
);
````


## -parameters
<dl>

### -param pInformationClass [out, optional]

<dd>
<p>A pointer to a driver-allocated variable that receives a <a href="..\wudfddi_types\ne-wudfddi-types--wdf-file-information-class.md">WDF_FILE_INFORMATION_CLASS</a>-typed value. This pointer is optional and can be <b>NULL</b>.</p>
</dd>

### -param pSizeInBytes [out, optional]

<dd>
<p>A pointer to a driver-allocated variable that receives the size, in bytes, of the file information. This pointer is optional and can be <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>Your driver can call <b>GetSetInformationParameters</b> to obtain the parameters that are associated with an I/O request, if the request type is <a href="..\wudfddi_types\ne-wudfddi-types--wdf-request-type.md">WdfRequestSetInformation</a>. The <i>pInformationClass</i> parameter identifies the type of file information that the driver should set, and the <i>pSizeInBytes</i> parameter specifies the size of the buffer that contains the information. The driver can call <a href="wdf.iwdfiorequest2_retrieveinputbuffer">IWDFIoRequest2::RetrieveInputBuffer</a> to obtain the buffer address. </p>

<p>Your driver must verify that the specified buffer size is large enough to contain the file information that the driver must set.</p>

<p>The following code example is part of an <a href="wdf.iqueuecallbackdefaultiohandler_ondefaultiohandler">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a> callback function. If the callback function receives a set information request, it retrieves the request's parameters. If the driver supports the specified type of information, it copies the information from the request's input buffer.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>End of support</p>
</th>
<td width="70%">
<p>Unavailable in UMDF 2.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.9</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
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
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest2_getqueryinformationparameters">IWDFIoRequest2::GetQueryInformationParameters</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::GetSetInformationParameters method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
