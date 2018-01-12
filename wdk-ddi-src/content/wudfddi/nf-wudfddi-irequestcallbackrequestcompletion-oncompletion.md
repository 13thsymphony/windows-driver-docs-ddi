---
UID: NF:wudfddi.IRequestCallbackRequestCompletion.OnCompletion
title: IRequestCallbackRequestCompletion::OnCompletion method
author: windows-driver-content
description: The OnCompletion method completes the specified request.
old-location: wdf\irequestcallbackrequestcompletion_oncompletion.htm
old-project: wdf
ms.assetid: 1a4787da-2813-4a7a-820a-5c078175aba5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IRequestCallbackRequestCompletion, IRequestCallbackRequestCompletion::OnCompletion, OnCompletion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IRequestCallbackRequestCompletion.OnCompletion
req.alt-loc: Wudfddi.h
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
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IRequestCallbackRequestCompletion::OnCompletion method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCompletion</b> method completes the specified request. 



## -syntax

````
void OnCompletion(
  [in] IWDFIoRequest               *pWdfRequest,
  [in] IWDFIoTarget                *pIoTarget,
  [in] IWDFRequestCompletionParams *pParams,
  [in] void                        *pContext
);
````


## -parameters

### -param pWdfRequest [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface that represents the framework request object. 


### -param pIoTarget [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiotarget.md">IWDFIoTarget</a> interface for the I/O target object that represents the lower driver in the stack where the request was previously sent. 


### -param pParams [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfrequestcompletionparams.md">IWDFRequestCompletionParams</a> interface for the parameters object for the completion request. 


### -param pContext [in]

A pointer to a buffer that contains context information that is related to the completion request.


## -returns
None


## -remarks
A driver registers the <a href="..\wudfddi\nn-wudfddi-irequestcallbackrequestcompletion.md">IRequestCallbackRequestCompletion</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559153">IWDFIoRequest::SetCompletionCallback</a> method. 


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-irequestcallbackrequestcompletion.md">IRequestCallbackRequestCompletion</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559153">IWDFIoRequest::SetCompletionCallback</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfrequestcompletionparams.md">IWDFRequestCompletionParams</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfiotarget.md">IWDFIoTarget</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IRequestCallbackRequestCompletion::OnCompletion method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

