---
UID: NF:winsplp.ImpersonatePrinterClient
title: ImpersonatePrinterClient function
author: windows-driver-content
description: ImpersonatePrinterClient resumes impersonation of the client, completing the operation begun by RevertToPrinterSelf.
old-location: print\impersonateprinterclient.htm
old-project: print
ms.assetid: 8e110b2a-9d13-4e2e-8f27-5a48d838fb3c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ImpersonatePrinterClient, ImpersonatePrinterClient function [Print Devices], print.impersonateprinterclient, spoolfnc_2eb48193-850d-43dc-8e9b-025c8187c49e.xml, winsplp/ImpersonatePrinterClient
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
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
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Spoolss.dll
api_name:
-	ImpersonatePrinterClient
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# ImpersonatePrinterClient function
ImpersonatePrinterClient resumes impersonation of the client, completing the operation begun by <a href="..\winsplp\nf-winsplp-reverttoprinterself.md">RevertToPrinterSelf</a>.

## Syntax

````
BOOL ImpersonatePrinterClient(
  _In_ HANDLE hToken
);
````

## Parameters

`hToken`

Caller-supplied handle to a thread. This parameter must have been previously returned by a call to <a href="..\winsplp\nf-winsplp-reverttoprinterself.md">RevertToPrinterSelf</a>.


## Return Value

If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>. The caller can obtain an error code by calling GetLastError (described in the Microsoft Windows SDK documentation).

## Remarks

This function must be called after a successful call to <a href="..\winsplp\nf-winsplp-reverttoprinterself.md">RevertToPrinterSelf</a>. It resumes impersonation of the client and cleans up the thread handle.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | winsplp.h (include Winsplp.h) |
| **Library** | Spoolss.lib |
| **DLL** | Spoolss.dll |

## See Also

<a href="..\winsplp\nf-winsplp-reverttoprinterself.md">RevertToPrinterSelf</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20ImpersonatePrinterClient function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>