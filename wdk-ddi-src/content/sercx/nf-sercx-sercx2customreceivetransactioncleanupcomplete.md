---
UID: NF.sercx.SerCx2CustomReceiveTransactionCleanupComplete
title: SerCx2CustomReceiveTransactionCleanupComplete function
author: windows-driver-content
description: The SerCx2CustomReceiveTransactionCleanupComplete method informs version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a custom-receive transaction.
old-location: serports\sercx2customreceivetransactioncleanupcomplete.htm
old-project: serports
ms.assetid: 45CCCD97-94FD-457B-8315-06DC701B22A2
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SerCx2CustomReceiveTransactionCleanupComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SerCx2CustomReceiveTransactionCleanupComplete
req.alt-loc: 2.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# SerCx2CustomReceiveTransactionCleanupComplete function



## -description
The <b>SerCx2CustomReceiveTransactionCleanupComplete</b> method informs version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a custom-receive transaction.



## -syntax

````
VOID SerCx2CustomReceiveTransactionCleanupComplete(
  [in] SERCX2CUSTOMRECEIVETRANSACTION CustomReceiveTransaction
);
````


## -parameters

### -param CustomReceiveTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive object. The serial controller driver previously called the <a href="serports.sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a> method to create this object.


## -returns
None.


## -remarks
After a custom-receive transaction ends, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_custom_receive_transaction_cleanup.md">EvtSerCx2CustomReceiveTransactionCleanup</a> event callback function, if it is implemented, to clean up the serial controller state. In response to this call, the driver should first do any clean-up work that is needed; then the driver must call <b>SerCx2CustomReceiveTransactionCleanupComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the next transaction until it is notified.

The serial controller driver must call <b>SerCx2CustomReceiveTransactionCleanupComplete</b> only in response to a call to the <i>EvtSerCx2CustomReceiveTransactionCleanup</i> function.

For more information, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.1.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>2.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_custom_receive_transaction_cleanup.md">EvtSerCx2CustomReceiveTransactionCleanup</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>
</dt>
<dt>
<a href="serports.sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2CustomReceiveTransactionCleanupComplete method%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

