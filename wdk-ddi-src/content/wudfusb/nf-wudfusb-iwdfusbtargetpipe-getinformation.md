---
UID: NF:wudfusb.IWDFUsbTargetPipe.GetInformation
title: IWDFUsbTargetPipe::GetInformation method
author: windows-driver-content
description: The GetInformation method retrieves information about a USB pipe (endpoint).
old-location: wdf\iwdfusbtargetpipe_getinformation.htm
old-project: wdf
ms.assetid: b1462a64-debf-441f-8964-4644074e5e53
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetInformation method, GetInformation method, IWDFUsbTargetPipe interface, GetInformation,IWDFUsbTargetPipe.GetInformation, IWDFUsbTargetPipe, IWDFUsbTargetPipe interface, GetInformation method, IWDFUsbTargetPipe::GetInformation, UMDFUSBref_4d7b2b77-fa26-45e2-8f3f-e0315d70f937.xml, umdf.iwdfusbtargetpipe_getinformation, wdf.iwdfusbtargetpipe_getinformation, wudfusb/IWDFUsbTargetPipe::GetInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
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
req.lib: wudfusb.h
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
-	IWDFUsbTargetPipe.GetInformation
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# GetInformation method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInformation</b> method retrieves information about a USB pipe (endpoint).

## Syntax

````
void GetInformation(
  [out] PWINUSB_PIPE_INFORMATION pInfo
);
````

## Parameters

`pInfo`

A pointer to a variable that receives USB pipe information.


## Return Value

None

## Remarks

After a UMDF driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560339">IWDFUsbInterface::RetrieveUsbPipeObject</a> method to retrieve a USB pipe object, the UMDF driver should retrieve information about the USB pipe. Therefore, the <b>GetInformation</b> method does not fail.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfusb.h (include Wudfusb.h) |
| **Library** | wudfusb.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560339">IWDFUsbInterface::RetrieveUsbPipeObject</a>



<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetPipe::GetInformation method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>