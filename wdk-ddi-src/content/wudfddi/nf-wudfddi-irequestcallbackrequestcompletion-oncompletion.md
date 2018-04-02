---
UID: NF:wudfddi.IRequestCallbackRequestCompletion.OnCompletion
title: IRequestCallbackRequestCompletion::OnCompletion method
author: windows-driver-content
description: The OnCompletion method completes the specified request.
old-location: wdf\irequestcallbackrequestcompletion_oncompletion.htm
old-project: wdf
ms.assetid: 1a4787da-2813-4a7a-820a-5c078175aba5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IRequestCallbackRequestCompletion, IRequestCallbackRequestCompletion interface, OnCompletion method, IRequestCallbackRequestCompletion::OnCompletion, OnCompletion method, OnCompletion method, IRequestCallbackRequestCompletion interface, OnCompletion,IRequestCallbackRequestCompletion.OnCompletion, UMDFRequestObjectRef_b3ec1892-f32f-4c52-80f6-8699a358ea8d.xml, umdf.irequestcallbackrequestcompletion_oncompletion, wdf.irequestcallbackrequestcompletion_oncompletion, wudfddi/IRequestCallbackRequestCompletion::OnCompletion
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IRequestCallbackRequestCompletion.OnCompletion
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IRequestCallbackRequestCompletion::OnCompletion method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCompletion</b> method completes the specified request.

## Syntax

```
void OnCompletion(
  IWDFIoRequest               *pWdfRequest,
  IWDFIoTarget                *pIoTarget,
  IWDFRequestCompletionParams *pParams,
  void                        *pContext
);
```

## Parameters

`pWdfRequest`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface that represents the framework request object.

`pIoTarget`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a> interface for the I/O target object that represents the lower driver in the stack where the request was previously sent.

`pParams`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560292">IWDFRequestCompletionParams</a> interface for the parameters object for the completion request.

`pContext`

A pointer to a buffer that contains context information that is related to the completion request.


## Return Value

None

## Remarks

A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556904">IRequestCallbackRequestCompletion</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559153">IWDFIoRequest::SetCompletionCallback</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wudfddi.h (include Wudfddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556904">IRequestCallbackRequestCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559153">IWDFIoRequest::SetCompletionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560292">IWDFRequestCompletionParams</a>