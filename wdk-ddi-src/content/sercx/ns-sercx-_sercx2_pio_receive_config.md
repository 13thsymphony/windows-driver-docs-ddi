---
UID: NS:sercx._SERCX2_PIO_RECEIVE_CONFIG
title: "_SERCX2_PIO_RECEIVE_CONFIG"
author: windows-driver-content
description: The SERCX2_PIO_RECEIVE_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new PIO-receive object.
old-location: serports\sercx2_pio_receive_config.htm
old-project: serports
ms.assetid: D95B1E7F-1966-4130-A410-3975B0438608
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSERCX2_PIO_RECEIVE_CONFIG, 2/PSERCX2_PIO_RECEIVE_CONFIG, 2/SERCX2_PIO_RECEIVE_CONFIG, PSERCX2_PIO_RECEIVE_CONFIG, PSERCX2_PIO_RECEIVE_CONFIG structure pointer [Serial Ports], SERCX2_PIO_RECEIVE_CONFIG, SERCX2_PIO_RECEIVE_CONFIG structure [Serial Ports], _SERCX2_PIO_RECEIVE_CONFIG, serports.sercx2_pio_receive_config"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	2.0\Sercx.h
api_name:
-	SERCX2_PIO_RECEIVE_CONFIG
product: Windows
targetos: Windows
req.typenames: SERCX2_PIO_RECEIVE_CONFIG, *PSERCX2_PIO_RECEIVE_CONFIG
req.product: Windows 10 or later.
---

# _SERCX2_PIO_RECEIVE_CONFIG structure
The <b>SERCX2_PIO_RECEIVE_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new PIO-receive object.

## Syntax
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

## Members


`Size`

The size, in bytes, of this structure. The <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.

`EvtSerCx2PioReceiveInitializeTransaction`

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_initialize_transaction.md">EvtSerCx2PioReceiveInitializeTransaction</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.

`EvtSerCx2PioReceiveCleanupTransaction`

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cleanup_transaction.md">EvtSerCx2PioReceiveCleanupTransaction</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.

`EvtSerCx2PioReceiveReadBuffer`

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_read_buffer.md">EvtSerCx2PioReceiveReadBuffer</a> event callback function. This member must point to a valid function.

`EvtSerCx2PioReceiveEnableReadyNotification`

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_enable_ready_notification.md">EvtSerCx2PioReceiveEnableReadyNotification</a> event callback function. This member must point to a valid function.

`EvtSerCx2PioReceiveCancelReadyNotification`

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cancel_ready_notification.md">EvtSerCx2PioReceiveCancelReadyNotification</a> event callback function. This member must point to a valid function.

## Remarks
The <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> method accepts a pointer to a <b>SERCX2_PIO_RECEIVE_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2PioReceiveCreate</b>, call the <a href="..\sercx\nf-sercx-sercx2_pio_receive_config_init.md">SERCX2_PIO_RECEIVE_CONFIG_INIT</a> function to initialize this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8.1. Supported starting with Windows 8.1. |
| **Header** | sercx.h |

## See Also

<a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_initialize_transaction.md">EvtSerCx2PioReceiveInitializeTransaction</a>



<a href="..\sercx\nf-sercx-sercx2_pio_receive_config_init.md">SERCX2_PIO_RECEIVE_CONFIG_INIT</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_enable_ready_notification.md">EvtSerCx2PioReceiveEnableReadyNotification</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_read_buffer.md">EvtSerCx2PioReceiveReadBuffer</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cancel_ready_notification.md">EvtSerCx2PioReceiveCancelReadyNotification</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cleanup_transaction.md">EvtSerCx2PioReceiveCleanupTransaction</a>