---
UID: NF:rxce.RxCeCancelConnectRequest
title: RxCeCancelConnectRequest function
author: windows-driver-content
description: RxCeCancelConnectRequest cancels a previously issued connection request. Note that this routine is not currently implemented.
old-location: ifsk\rxcecancelconnectrequest.htm
old-project: ifsk
ms.assetid: 32893a68-68ac-4bac-ab0f-1d07a1e873f3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxCeCancelConnectRequest, RxCeCancelConnectRequest routine [Installable File System Drivers], ifsk.rxcecancelconnectrequest, rxce/RxCeCancelConnectRequest, rxref_b7978600-a1ca-4713-b170-bc1f365f2f96.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxce.h
api_name:
-	RxCeCancelConnectRequest
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---


# RxCeCancelConnectRequest function
<b>RxCeCancelConnectRequest</b> cancels a previously issued connection request. Note that this routine is not currently implemented.

## Syntax

````
NTSTATUS RxCeCancelConnectRequest(
  _In_ PRXCE_ADDRESS                pLocalAddress,
  _In_ PUNICODE_STRING              pServerName,
  _In_ PRXCE_CONNECTION_INFORMATION pConnectionInformation
);
````

## Parameters

`pLocalAddress`

A pointer to the local RDBSS connection engine address on which the previously issued connection request was made.

`pServerName`

A pointer to the name of the server on which the previous connection request was made.

`pConnectionInformation`

A pointer to the connection information that specifies the remote address. on which the previously issued connection request was made.


## Return Value

<b>RxCeCancelConnectRequest</b> returns STATUS_NOT_IMPLEMENTED since this routine is not currently implemented.

## Remarks

<b>RXCE_CONNECTION_INFORMATION</b> is a typedef for a <b>TDI_CONNECTION_INFORMATION</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | rxce.h (include Rxce.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565085">TDI_CONNECTION_INFORMATION</a>



<a href="..\rxce\nf-rxce-rxceteardownconnection.md">RxCeTearDownConnection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeCancelConnectRequest routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>