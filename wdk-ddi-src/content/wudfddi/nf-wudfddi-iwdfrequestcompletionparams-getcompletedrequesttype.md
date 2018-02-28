---
UID: NF:wudfddi.IWDFRequestCompletionParams.GetCompletedRequestType
title: IWDFRequestCompletionParams::GetCompletedRequestType method
author: windows-driver-content
description: The GetCompletedRequestType method retrieves the type of operation that the request to be completed contains.
old-location: wdf\iwdfrequestcompletionparams_getcompletedrequesttype.htm
old-project: wdf
ms.assetid: 1977828d-61bb-4649-bfa6-e5e82775258e
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: GetCompletedRequestType method, GetCompletedRequestType method, IWDFRequestCompletionParams interface, GetCompletedRequestType,IWDFRequestCompletionParams.GetCompletedRequestType, IWDFRequestCompletionParams, IWDFRequestCompletionParams interface, GetCompletedRequestType method, IWDFRequestCompletionParams::GetCompletedRequestType, UMDFRequestObjectRef_97c61d1b-059f-44d7-9d3a-7c031099d669.xml, umdf.iwdfrequestcompletionparams_getcompletedrequesttype, wdf.iwdfrequestcompletionparams_getcompletedrequesttype, wudfddi/IWDFRequestCompletionParams::GetCompletedRequestType
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
-	IWDFRequestCompletionParams.GetCompletedRequestType
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# GetCompletedRequestType method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCompletedRequestType</b> method retrieves the type of operation that the request to be completed contains.

## Syntax

````
WDF_REQUEST_TYPE  GetCompletedRequestType();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetCompletedRequestType</b> returns a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE</a>-typed value that identifies the request type and why the request was sent to the driver.


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

<a href="..\wudfddi\nn-wudfddi-iwdfrequestcompletionparams.md">IWDFRequestCompletionParams</a>



<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRequestCompletionParams::GetCompletedRequestType method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>