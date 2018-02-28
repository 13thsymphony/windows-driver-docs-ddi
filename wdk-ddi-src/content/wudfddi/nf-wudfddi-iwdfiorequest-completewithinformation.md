---
UID: NF:wudfddi.IWDFIoRequest.CompleteWithInformation
title: IWDFIoRequest::CompleteWithInformation method
author: windows-driver-content
description: The CompleteWithInformation method completes a request with the supplied information.
old-location: wdf\iwdfiorequest_completewithinformation.htm
old-project: wdf
ms.assetid: 43089473-3255-4016-8d51-f5ad4261bd8d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: CompleteWithInformation method, CompleteWithInformation method, IWDFIoRequest interface, CompleteWithInformation,IWDFIoRequest.CompleteWithInformation, IWDFIoRequest, IWDFIoRequest interface, CompleteWithInformation method, IWDFIoRequest::CompleteWithInformation, UMDFRequestObjectRef_c01f0d7b-3b4d-442c-8425-a99c064609ee.xml, umdf.iwdfiorequest_completewithinformation, wdf.iwdfiorequest_completewithinformation, wudfddi/IWDFIoRequest::CompleteWithInformation
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest.CompleteWithInformation
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# CompleteWithInformation method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CompleteWithInformation</b> method completes a request with the supplied information.

## Syntax

````
void CompleteWithInformation(
  [in] HRESULT CompletionStatus,
  [in] SIZE_T  Information
);
````

## Parameters

`CompletionStatus`

A status value to complete the request with.

`Information`

Additional driver-supplied information that is related to the I/O operation.

For read, write, and device I/O control operations, the driver should supply the number of bytes that are transferred.


## Return Value

None

## Remarks

For more information about completing an I/O request, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.

For a code example of how to use the <b>CompleteWithInformation</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::CompleteWithInformation method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>