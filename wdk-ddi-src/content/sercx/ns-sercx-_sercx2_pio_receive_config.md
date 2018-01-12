---
UID: NS:sercx._SERCX2_PIO_RECEIVE_CONFIG
title: _SERCX2_PIO_RECEIVE_CONFIG
author: windows-driver-content
description: The SERCX2_PIO_RECEIVE_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new PIO-receive object.
old-location: serports\sercx2_pio_receive_config.htm
old-project: serports
ms.assetid: D95B1E7F-1966-4130-A410-3975B0438608
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SERCX2_PIO_RECEIVE_CONFIG, SERCX2_PIO_RECEIVE_CONFIG, *PSERCX2_PIO_RECEIVE_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SERCX2_PIO_RECEIVE_CONFIG
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
req.irql: Any IRQL
req.typenames: SERCX2_PIO_RECEIVE_CONFIG, *PSERCX2_PIO_RECEIVE_CONFIG
req.product: Windows 10 or later.
---

# _SERCX2_PIO_RECEIVE_CONFIG structure



## -description
The <b>SERCX2_PIO_RECEIVE_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new PIO-receive object.



## -syntax

````
typedef struct _SERCX2_PIO_RECEIVE_CONFIG {
  ULONG                                            Size;
  PFN_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION    EvtSerCx2PioReceiveInitializeTransaction;
  PFN_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION       EvtSerCx2PioReceiveCleanupTransaction;
  PFN_SERCX2_PIO_RECEIVE_READ_BUFFER               EvtSerCx2PioReceiveReadBuffer;
  PFN_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION EvtSerCx2PioReceiveEnableReadyNotification;
  PFN_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION EvtSerCx2PioReceiveCancelReadyNotification;
} SERCX2_PIO_RECEIVE_CONFIG, *PSERCX2_PIO_RECEIVE_CONFIG;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure. The <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field EvtSerCx2PioReceiveInitializeTransaction

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_initialize_transaction.md">EvtSerCx2PioReceiveInitializeTransaction</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2PioReceiveCleanupTransaction

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cleanup_transaction.md">EvtSerCx2PioReceiveCleanupTransaction</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2PioReceiveReadBuffer

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_read_buffer.md">EvtSerCx2PioReceiveReadBuffer</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioReceiveEnableReadyNotification

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_enable_ready_notification.md">EvtSerCx2PioReceiveEnableReadyNotification</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioReceiveCancelReadyNotification

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cancel_ready_notification.md">EvtSerCx2PioReceiveCancelReadyNotification</a> event callback function. This member must point to a valid function.


## -remarks
The <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> method accepts a pointer to a <b>SERCX2_PIO_RECEIVE_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2PioReceiveCreate</b>, call the <a href="..\sercx\nf-sercx-sercx2_pio_receive_config_init.md">SERCX2_PIO_RECEIVE_CONFIG_INIT</a> function to initialize this structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 8.1.

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
</table>

## -see-also
<dl>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cancel_ready_notification.md">EvtSerCx2PioReceiveCancelReadyNotification</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cleanup_transaction.md">EvtSerCx2PioReceiveCleanupTransaction</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2_pio_receive_config_init.md">SERCX2_PIO_RECEIVE_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_enable_ready_notification.md">EvtSerCx2PioReceiveEnableReadyNotification</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_initialize_transaction.md">EvtSerCx2PioReceiveInitializeTransaction</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_read_buffer.md">EvtSerCx2PioReceiveReadBuffer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_PIO_RECEIVE_CONFIG structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

