---
UID: NF:wdfrequest.WdfRequestGetRequestorProcessId
title: WdfRequestGetRequestorProcessId function
author: windows-driver-content
description: The WdfRequestGetRequestorProcessId method retrieves the identifier of the process that sent an I/O request.
old-location: wdf\wdfrequestgetrequestorprocessid.htm
old-project: wdf
ms.assetid: F2CE35C8-F3BA-49E3-AE27-2FC5BFEC2D58
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfRequestGetRequestorProcessId, WdfRequestGetRequestorProcessId method, wdf.wdfrequestgetrequestorprocessid, wdfrequest/WdfRequestGetRequestorProcessId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.21
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.lib
req.dll: WUDFx02000.dll; TBD
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfRequestGetRequestorProcessId
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfRequestGetRequestorProcessId function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestGetRequestorProcessId</b> method retrieves the identifier of the process that sent an I/O request.

## Syntax

````
ULONG WdfRequestGetRequestorProcessId(
  _In_ WDFREQUEST Request
);
````

## Parameters

`Request`

A handle to a framework request object.


## Return Value

<b>WdfRequestGetRequestorProcessId</b> returns the identifier of the process that sent the I/O request.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.21 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.lib |
| **DLL** | WUDFx02000.dll; TBD |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="..\wdffileobject\nf-wdffileobject-wdffileobjectgetinitiatorprocessid.md">WdfFileObjectGetInitiatorProcessId</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestGetRequestorProcessId method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>