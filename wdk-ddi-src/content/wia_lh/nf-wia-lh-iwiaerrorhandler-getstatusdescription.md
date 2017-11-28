---
UID: NF.wia_lh.IWiaErrorHandler.GetStatusDescription
title: IWiaErrorHandler::GetStatusDescription
author: windows-driver-content
description: The system UI calls the WiaErrorHandler::GetStatusDescription method to provide the user with extra information about an error, if the user requests this information. This method is implemented by a driver's UI extension.
old-location: image\iwiaerrorhandler_getstatusdescription.htm
old-project: image
ms.assetid: c3b5622d-9d51-4008-abb0-c8a60c4a6b16
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: IWiaErrorHandler, GetStatusDescription, IWiaErrorHandler::GetStatusDescription
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wia_lh.h
req.include-header: Wia.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IWiaErrorHandler.GetStatusDescription
req.alt-loc: wia_lh.h
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
req.iface: IWiaErrorHandler
req.product: Windows 10 or later.
---

# IWiaErrorHandler::GetStatusDescription method



## -description
<p> The system UI calls the <b>WiaErrorHandler::GetStatusDescription</b> method to provide the user with extra information about an error, if the user requests this information. This method is implemented by a driver's UI extension.</p>


## -syntax

````
HRESULT GetStatusDescription(
  [in]  LONG      lFlags,
  [in]  IWiaItem2 *pWiaItem2,
  [in]  HRESULT   hrStatus,
  [out] BSTR      *pbstrDescription
);
````


## -parameters
<dl>

### -param <i>lFlags</i> [in]

<dd>
<p>Currently unused. Should be set to zero. </p>
</dd>

### -param <i>pWiaItem2</i> [in]

<dd>
<p>Pointer to the <b>IWiaItem2</b> item being transferred. <b>IWiaItem2</b> is described in the Microsoft Windows SDK documentation.</p>
</dd>

### -param <i>hrStatus</i> [in]

<dd>
<p>HRESULT variable that contains the status code received by the WIA transfer method, for example the <b>IWiaDataCallback::BandedDataCallback</b> method (described in the Windows SDK documentation).</p>
</dd>

### -param <i>pbstrDescription</i> [out]

<dd>
<p>Pointer to a BSTR that receives a description of the status or error encountered during the transfer. This parameter cannot be <b>NULL</b>. The driver must allocate the string using the <b>SysAllocString</b> function and the caller must free the string using the <b>SysFreeString</b> function. The <b>SysFreeString</b> and <b>SysAllocString </b>functions are described in the Windows SDK documentation.</p>
</dd>
</dl>

## -returns
<p>Returns a standard COM error code if an error occurs, or one of the following:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The<i> pbstrDescription</i> parameter contains a valid BSTR pointer.</p><dl>
<dt><b>WIA_STATUS_NOT_HANDLED</b></dt>
</dl><p>The value in the <i>hrStatus</i> parameter is unknown to the extension and no description is available.</p>

<p> </p>

## -remarks
<p>In order for an application to call <b>IWiaErrorHandler::GetStatusDescription</b>, the application must call <b>IWiaItem2::GetExtension</b> first to receive an interface pointer to the error handling extension. An application must pass "ErrorHandler" as bstrName and IID_IWiaErrorHandler as riidExtensionInterface. An application should pass 0 as lFlags to ensure upward compatibility.</p>

<p>The implementation of <b>IWiaErrorHandler::GetStatusDescription</b> should return S_OK for all the device status codes (<i>hrStatus</i>) that the implementation of <b>IWiaErrorHandler::ReportStatus </b>handles, and WIA_STATUS_NOT_HANDLED for those that <b>IWiaErrorHandler::ReportStatus </b>does not handle.</p>

<p>In order for an application to call <b>IWiaErrorHandler::GetStatusDescription</b>, the application must call <b>IWiaItem2::GetExtension</b> first to receive an interface pointer to the error handling extension. An application must pass "ErrorHandler" as bstrName and IID_IWiaErrorHandler as riidExtensionInterface. An application should pass 0 as lFlags to ensure upward compatibility.</p>

<p>The implementation of <b>IWiaErrorHandler::GetStatusDescription</b> should return S_OK for all the device status codes (<i>hrStatus</i>) that the implementation of <b>IWiaErrorHandler::ReportStatus </b>handles, and WIA_STATUS_NOT_HANDLED for those that <b>IWiaErrorHandler::ReportStatus </b>does not handle.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wia_lh.h (include Wia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543909">IWiaErrorHandler::ReportStatus</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaErrorHandler::GetStatusDescription method%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
