---
UID: NE:sercx._SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
title: "_SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS"
author: windows-driver-content
description: The SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS enumeration defines constants that indicate whether process is being made toward completing a custom-receive transaction.
old-location: serports\sercx2_custom_receive_transaction_progress.htm
old-project: serports
ms.assetid: B832554C-FB37-416F-9586-EFAB5A3633E5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PSERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, SERCX2_CUSTOM_RECEIVE_BYTES_TRANSFERRED, 2/SERCX2_CUSTOM_RECEIVE_NO_PROGRESS, serports.sercx2_custom_receive_transaction_progress, SERCX2_CUSTOM_RECEIVE_NO_PROGRESS, _SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, 2/SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS enumeration [Serial Ports], 2/SERCX2_CUSTOM_RECEIVE_BYTES_TRANSFERRED"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sercx.h
req.include-header: 
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	2.0\Sercx.h
apiname:
-	SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
product: Windows
targetos: Windows
req.typenames: SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS, *PSERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS
req.product: Windows 10 or later.
---

# _SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS Enumeration
The <b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS</b> enumeration defines constants that indicate whether process is being made toward completing a custom-receive transaction.

## Syntax
````
typedef enum _SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS { 
  SERCX2_CUSTOM_RECEIVE_NO_PROGRESS,
  SERCX2_CUSTOM_RECEIVE_BYTES_TRANSFERRED
} SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS;
````

## Constants

<table>
            
                <tr>
                    <td>SerCx2CustomReceiveTransactionBytesTransferred</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>SerCx2CustomReceiveTransactionNoProgress</td>
                    <td></td>
                </tr>
</table>

    ## Remarks

        The constants in this enumeration are used by the <a href="..\sercx\nf-sercx-sercx2customreceivetransactionreportprogress.md">SerCx2CustomReceiveTransactionReportProgress</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sercx.h |

    ## See Also

        <a href="..\sercx\nf-sercx-sercx2customreceivetransactionreportprogress.md">SerCx2CustomReceiveTransactionReportProgress</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>