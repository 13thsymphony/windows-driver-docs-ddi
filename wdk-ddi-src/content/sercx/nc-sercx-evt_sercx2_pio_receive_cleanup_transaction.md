---
UID: NC.sercx.EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION
title: EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION
author: windows-driver-content
description: The EvtSerCx2PioReceiveCleanupTransaction event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller's hardware state after a PIO-receive transaction ends.
old-location: serports\evtsercx2pioreceivecleanuptransaction.htm
old-project: serports
ms.assetid: 2CFCF5D9-23F8-4571-972A-0BE48EB2D046
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SENSOR_VALUE_PAIR, PSENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
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
req.alt-api: EvtSerCx2PioReceiveCleanupTransaction
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION callback



## -description
The <i>EvtSerCx2PioReceiveCleanupTransaction</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller's hardware state after a PIO-receive transaction ends.



## -prototype

````
EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION EvtSerCx2PioReceiveCleanupTransaction;

VOID EvtSerCx2PioReceiveCleanupTransaction(
  _In_ SERCX2PIORECEIVE PioReceive
)
{ ... }
````


## -parameters

### -param PioReceive [in]

A <a href="serports.sercx2pioreceive_object_handle">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="serports.sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method to create this object.


## -returns
None.


## -remarks
Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the call to the <a href="serports.sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method that creates the PIO-receive object.

Your serial controller driver should implement an <i>EvtSerCx2PioReceiveCleanupTransaction</i> function if it needs to clean up the serial controller state at the end of a PIO-receive transaction. SerCx2 calls this function, if it is implemented, after a PIO-receive transaction ends. In response to the <i>EvtSerCx2PioReceiveCleanupTransaction</i> call, the serial controller driver must call the <a href="serports.sercx2pioreceivecleanuptransactioncomplete">SerCx2PioReceiveCleanupTransactionComplete</a> method to notify SerCx2 after the clean-up work is done.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.

To define an <i>EvtSerCx2PioReceiveCleanupTransaction</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioReceiveCleanupTransaction</i> callback function that is named <code>MyPioReceiveCleanupTransaction</code>, use the <b>EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION</b> function type, as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
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
Called at IRQL &lt;= DISPATCH_LEVEL.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="serports.sercx2pioreceive_object_handle">SERCX2PIORECEIVE</a>
</dt>
<dt>
<a href="serports.sercx2pioreceivecreate">SerCx2PioReceiveCreate</a>
</dt>
<dt>
<a href="serports.sercx2pioreceivecleanuptransactioncomplete">SerCx2PioReceiveCleanupTransactionComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

