---
UID: NF:prnasntp.RouterUnregisterForPrintAsyncNotifications
title: RouterUnregisterForPrintAsyncNotifications function
author: windows-driver-content
description: The RouterUnregisterForPrintAsyncNotifications function unregisters for receiving asynchronous notifications associated with a printer or print server.
old-location: print\routerunregisterforprintasyncnotifications.htm
old-project: print
ms.assetid: 67909e35-fae2-40b7-b39f-58576e932332
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RouterUnregisterForPrintAsyncNotifications, RouterUnregisterForPrintAsyncNotifications function [Print Devices], print.routerunregisterforprintasyncnotifications, prnasntp/RouterUnregisterForPrintAsyncNotifications, spoolfnc_3c629be8-f1d8-43fb-b225-582e4bb76c51.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prnasntp.h
req.include-header: Prnasntp.h
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
-	RouterUnregisterForPrintAsyncNotifications
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---


# RouterUnregisterForPrintAsyncNotifications function
The <code>RouterUnregisterForPrintAsyncNotifications</code> function unregisters for receiving asynchronous notifications associated with a printer or print server.

## Syntax

```
HRESULT RouterUnregisterForPrintAsyncNotifications(
  HANDLE hNotify
);
```

## Parameters

`hNotify`

The registration handle returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562024">RouterRegisterForPrintAsyncNotifications</a> function.


## Return Value

This function returns S_OK on success, and a standard COM error code otherwise.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prnasntp.h (include Prnasntp.h) |
| **Library** | Spoolss.lib |
| **DLL** | Spoolss.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562024">RouterRegisterForPrintAsyncNotifications</a>