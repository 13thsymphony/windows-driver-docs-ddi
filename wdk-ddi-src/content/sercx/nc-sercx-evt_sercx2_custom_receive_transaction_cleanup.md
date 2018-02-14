---
UID: NC:sercx.EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_CLEANUP
title: EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_CLEANUP
author: windows-driver-content
description: The EvtSerCx2CustomReceiveTransactionCleanup event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller's hardware state after a custom-receive transaction ends.
old-location: serports\evtsercx2customreceivetransactioncleanup.htm
old-project: serports
ms.assetid: 72AF3D52-D109-42A7-9F25-14A3F5EDC94A
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2customreceivetransactioncleanup, EvtSerCx2CustomReceiveTransactionCleanup callback function [Serial Ports], EvtSerCx2CustomReceiveTransactionCleanup, EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_CLEANUP, EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_CLEANUP, 2/EvtSerCx2CustomReceiveTransactionCleanup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	2.0\Sercx.h
apiname:
-	EvtSerCx2CustomReceiveTransactionCleanup
product: Windows
targetos: Windows
req.typenames: "*PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR"
req.product: Windows 10 or later.
---


# EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_CLEANUP function
The <i>EvtSerCx2CustomReceiveTransactionCleanup</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller's hardware state after a custom-receive transaction ends.

## Syntax

```
EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_CLEANUP EvtSercx2CustomReceiveTransactionCleanup;

void EvtSercx2CustomReceiveTransactionCleanup(
  SERCX2CUSTOMRECEIVETRANSACTION CustomReceiveTransaction
)
{...}
```

## Parameters

`CustomReceiveTransaction`

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive-transaction object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a> method to create this object.


## Return Value

None.

## Remarks

Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a> call that creates the custom-receive object.

Your serial controller driver should implement an <i>EvtSerCx2CustomReceiveTransactionCleanup</i> function if it needs to clean up the serial controller state at the end of a custom-receive transaction. SerCx2 calls this function, if it is implemented, after a custom-receive transaction ends. In response to the <i>EvtSerCx2CustomReceiveTransactionCleanup</i> call, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2customreceivetransactioncleanupcomplete.md">SerCx2CustomReceiveTransactionCleanupComplete</a> method to notify SerCx2 after the clean-up work is done.

For more information, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2CustomReceiveTransactionCleanup</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2CustomReceiveTransactionCleanup</i> callback function that is named <code>MyCustomReceiveTransactionCleanup</code>, use the <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_CLEANUP</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_CLEANUP  MyCustomReceiveTransactionCleanup;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyCustomReceiveTransactionCleanup(
    SERCX2CUSTOMRECEIVETRANSACTION  CustomReceiveTransaction
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_CLEANUP</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_CLEANUP</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1. Available starting with Windows 8.1. |
| **Target Platform** | Desktop |
| **Header** | sercx.h |
| **IRQL** | Called at IRQL <= DISPATCH_LEVEL. |

## See Also

<a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="..\sercx\nf-sercx-sercx2customreceivetransactioncleanupcomplete.md">SerCx2CustomReceiveTransactionCleanupComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_CLEANUP callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>