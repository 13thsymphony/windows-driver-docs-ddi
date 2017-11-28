---
UID: NC.sercx.EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION
title: EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION
author: windows-driver-content
description: The EvtSerCx2PioReceiveEnableReadyNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the serial controller receives new data.
old-location: serports\evtsercx2pioreceiveenablereadynotification.htm
old-project: serports
ms.assetid: DDD17DF3-9457-40D1-BE18-0A1CAED1389B
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
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
req.alt-api: EvtSerCx2PioReceiveEnableReadyNotification
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
req.iface: 
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION callback



## -description
<p>The <i>EvtSerCx2PioReceiveEnableReadyNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the serial controller receives new data.</p>


## -prototype

````
EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION EvtSerCx2PioReceiveEnableReadyNotification;

VOID EvtSerCx2PioReceiveEnableReadyNotification(
  _In_ SERCX2PIORECEIVE PioReceive
)
{ ... }
````


## -parameters
<dl>

### -param <i>PioReceive</i> [in]

<dd>
<p>A <a href="serports.sercx2pioreceive_object_handle">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a> method to create this object.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>Your serial controller driver must implement this function. The driver registers the function in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a> call that creates the PIO-receive object.</p>

<p>After the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function is called to enable a ready notification for a PIO-receive transaction, the serial controller driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265266">SerCx2PioReceiveReady</a> method to notify SerCx2 when the driver detects that one or more bytes of data are available to be read from the receive FIFO in the serial controller hardware. If data is already available in the receive FIFO when the ready notification is enabled, the driver immediately calls this method to notify SerCx2.</p>

<p>The ready notification for a PIO-receive transaction is a one-shot notification. After sending a ready notification to SerCx2, the serial controller driver sends no further notifications until SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable another notification.</p>

<p>An <a href="..\sercx\nc-sercx-evt-sercx2-pio-receive-read-buffer.md">EvtSerCx2PioReceiveReadBuffer</a> event callback function call might only partially complete a PIO-receive transaction because no more data is immediately available to be read from the receive FIFO. In this case, SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable a ready notification, in which case the serial controller driver must notify SerCx2 when the receive FIFO contains more data. In response to this notification, SerCx2 resumes the partially completed receive transaction by calling the <i>EvtSerCx2PioReceiveReadBuffer</i> function again.</p>

<p>Typically, an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function enables an interrupt that occurs when the serial controller has more data available to be read.  In response to this interrupt, the serial controller driver calls <b>SerCx2PioReceiveReady</b>.</p>

<p>No more than one ready notification can be pending at a time. After SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable a ready notification, SerCx2 does not call this function again until the controller driver calls <b>SerCx2PioReceiveReady</b>.</p>

<p>SerCx2 never calls the <i>EvtSerCx2PioReceiveReadBuffer</i> function when the ready notification is enabled.</p>

<p>A pending ready notification can be canceled if the associated read request times out or is canceled. To cancel a ready notification for a PIO-receive transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt-sercx2-pio-receive-cancel-ready-notification.md">EvtSerCx2PioReceiveCancelReadyNotification</a> event callback function.</p>

<p>SerCx2 uses ready notifications to efficiently manage interval time-outs that occur during the handling of read requests that are processed as PIO-receive transactions.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.</p>

<p>To define an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> callback function that is named <code>MyPioReceiveEnableReadyNotification</code>, use the <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type, as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.</p>

<p>Your serial controller driver must implement this function. The driver registers the function in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a> call that creates the PIO-receive object.</p>

<p>After the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function is called to enable a ready notification for a PIO-receive transaction, the serial controller driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265266">SerCx2PioReceiveReady</a> method to notify SerCx2 when the driver detects that one or more bytes of data are available to be read from the receive FIFO in the serial controller hardware. If data is already available in the receive FIFO when the ready notification is enabled, the driver immediately calls this method to notify SerCx2.</p>

<p>The ready notification for a PIO-receive transaction is a one-shot notification. After sending a ready notification to SerCx2, the serial controller driver sends no further notifications until SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable another notification.</p>

<p>An <a href="..\sercx\nc-sercx-evt-sercx2-pio-receive-read-buffer.md">EvtSerCx2PioReceiveReadBuffer</a> event callback function call might only partially complete a PIO-receive transaction because no more data is immediately available to be read from the receive FIFO. In this case, SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable a ready notification, in which case the serial controller driver must notify SerCx2 when the receive FIFO contains more data. In response to this notification, SerCx2 resumes the partially completed receive transaction by calling the <i>EvtSerCx2PioReceiveReadBuffer</i> function again.</p>

<p>Typically, an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function enables an interrupt that occurs when the serial controller has more data available to be read.  In response to this interrupt, the serial controller driver calls <b>SerCx2PioReceiveReady</b>.</p>

<p>No more than one ready notification can be pending at a time. After SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable a ready notification, SerCx2 does not call this function again until the controller driver calls <b>SerCx2PioReceiveReady</b>.</p>

<p>SerCx2 never calls the <i>EvtSerCx2PioReceiveReadBuffer</i> function when the ready notification is enabled.</p>

<p>A pending ready notification can be canceled if the associated read request times out or is canceled. To cancel a ready notification for a PIO-receive transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt-sercx2-pio-receive-cancel-ready-notification.md">EvtSerCx2PioReceiveCancelReadyNotification</a> event callback function.</p>

<p>SerCx2 uses ready notifications to efficiently manage interval time-outs that occur during the handling of read requests that are processed as PIO-receive transactions.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.</p>

<p>To define an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> callback function that is named <code>MyPioReceiveEnableReadyNotification</code>, use the <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type, as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.1.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>2.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Called at IRQL &lt;= DISPATCH_LEVEL.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\sercx\nc-sercx-evt-sercx2-pio-receive-cancel-ready-notification.md">EvtSerCx2PioReceiveCancelReadyNotification</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt-sercx2-pio-receive-cleanup-transaction.md">EvtSerCx2PioReceiveCleanupTransaction</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>
</dt>
<dt>
<a href="serports.sercx2pioreceive_object_handle">SERCX2PIORECEIVE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265266">SerCx2PioReceiveReady</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION callback function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
