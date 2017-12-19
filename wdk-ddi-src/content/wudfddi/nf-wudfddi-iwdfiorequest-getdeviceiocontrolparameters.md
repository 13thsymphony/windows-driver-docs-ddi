---
UID: NF.wudfddi.IWDFIoRequest.GetDeviceIoControlParameters
title: IWDFIoRequest::GetDeviceIoControlParameters method
author: windows-driver-content
description: The GetDeviceIoControlParameters method retrieves the request parameters for a device I/O control-type request.
old-location: wdf\iwdfiorequest_getdeviceiocontrolparameters.htm
old-project: wdf
ms.assetid: 96de6f7a-da1d-44a6-b1f7-44859312a662
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFIoRequest, IWDFIoRequest::GetDeviceIoControlParameters, GetDeviceIoControlParameters
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
req.alt-api: IWDFIoRequest.GetDeviceIoControlParameters
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

# IWDFIoRequest::GetDeviceIoControlParameters method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDeviceIoControlParameters</b> method retrieves the request parameters for a device I/O control-type request.



## -syntax

````
void  GetDeviceIoControlParameters(
  [out] ULONG  *pControlCode,
  [out] SIZE_T *pInBufferSize,
  [out] SIZE_T *pOutBufferSize
);
````


## -parameters

### -param pControlCode [out]

A pointer to a variable that receives the control code that identifies the specific operation to be performed.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pInBufferSize [out]

A pointer to a variable that receives the size, in bytes, of the input data buffer for the request. To retrieve the input data buffer, the driver calls the <a href="wdf.iwdfiorequest_getinputmemory">IWDFIoRequest::GetInputMemory</a> method.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pOutBufferSize [out]

A pointer to a variable that receives the size, in bytes, of the output data buffer for the request. To retrieve the output data buffer, the driver calls the <a href="wdf.iwdfiorequest_getoutputmemory">IWDFIoRequest::GetOutputMemory</a> method.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -returns
None


## -remarks
The call to <b>GetDeviceIoControlParameters</b> fails if the request type is not a device I/O control type.

Although the driver can optionally specify <b>NULL</b> for each of the <i>pControlCode</i>, <i>pInBufferSize</i>, and <i>pOutBufferSize</i> parameters, the driver must specify at least one non-<b>NULL</b> parameter for <b>GetDeviceIoControlParameters</b> to execute successfully.


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
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest_getinputmemory">IWDFIoRequest::GetInputMemory</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest_getoutputmemory">IWDFIoRequest::GetOutputMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::GetDeviceIoControlParameters method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

