---
UID: NS:sercx._SERCX_CONFIG
title: "_SERCX_CONFIG"
author: windows-driver-content
description: The SERCX_CONFIG structure contains configuration information for the serial framework extension (SerCx).
old-location: serports\sercx_config.htm
old-project: serports
ms.assetid: 2CBCBA07-C489-4475-A856-8748FBFDC141
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSERCX_CONFIG, 1/PSERCX_CONFIG, 1/SERCX_CONFIG, PSERCX_CONFIG, PSERCX_CONFIG structure pointer [Serial Ports], SERCX_CONFIG, SERCX_CONFIG structure [Serial Ports], _SERCX_CONFIG, serports.sercx_config"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
-	1.0\Sercx.h
api_name:
-	SERCX_CONFIG
product: Windows
targetos: Windows
req.typenames: SERCX_CONFIG, *PSERCX_CONFIG
req.product: Windows 10 or later.
---

# _SERCX_CONFIG structure
The <b>SERCX_CONFIG</b> structure contains configuration information for the serial framework extension (SerCx).

## Syntax
````
typedef struct _SERCX_CONFIG {
  ULONG                     Size;
  WDF_TRI_STATE             PowerManaged;
  PFN_SERCX_FILEOPEN        EvtSerCxFileOpen;
  PFN_SERCX_FILECLOSE       EvtSerCxFileClose;
  PFN_SERCX_FILECLEANUP     EvtSerCxFileCleanup;
  PFN_SERCX_TRANSMIT        EvtSerCxTransmit;
  PFN_SERCX_RECEIVE         EvtSerCxReceive;
  PFN_SERCX_WAITMASK        EvtSerCxWaitmask;
  PFN_SERCX_PURGE           EvtSerCxPurge;
  PFN_SERCX_CONTROL         EvtSerCxControl;
  PFN_SERCX_APPLY_CONFIG    EvtSerCxApplyConfig;
  PFN_SERCX_TRANSMIT_CANCEL EvtSerCxTransmitCancel;
  PFN_SERCX_RECEIVE_CANCEL  EvtSerCxReceiveCancel;
} SERCX_CONFIG, *PSERCX_CONFIG;
````

## Members


`Size`

The size, in bytes, of this structure. The <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.

`PowerManaged`

Whether the controller queue should be power-managed. If set to <b>WdfTrue</b>, the controller queue should be power-managed.  If set to <b>WdfFalse</b>, the controller queue not be power-managed. If set to <b>WdfDefault</b>, the controller queue should be power-managed unless the driver calls the <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetfilter.md">WdfFdoInitSetFilter</a> method. For more information, see the description of the <b>PowerManaged</b> member in <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a>.

`EvtSerCxFileOpen`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_fileopen.md">EvtSerCxFileOpen</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxFileClose`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_fileclose.md">EvtSerCxFileClose</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxFileCleanup`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_filecleanup.md">EvtSerCxFileCleanup</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxTransmit`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_transmit.md">EvtSerCxTransmit</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxReceive`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_receive.md">EvtSerCxReceive</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxWaitmask`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_waitmask.md">EvtSerCxWaitmask</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxPurge`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_purge.md">EvtSerCxPurge</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxControl`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_control.md">EvtSerCxControl</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxApplyConfig`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_apply_config.md">EvtSerCxApplyConfig</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxTransmitCancel`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_transmit_cancel.md">EvtSerCxTransmitCancel</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxReceiveCancel`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_receive_cancel.md">EvtSerCxReceiveCancel</a> callback function. This member is optional and can be set to NULL.

## Remarks
Before this structure is passed to the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method, it must be initialized by the <a href="..\sercx\nf-sercx-sercx_config_init.md">SERCX_CONFIG_INIT</a> function, and then modified by the controller driver to set the callback function pointers and the <b>PowerManaged</b> member.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | sercx.h |

## See Also

<a href="..\sercx\nc-sercx-evt_sercx_receive_cancel.md">EvtSerCxReceiveCancel</a>



<a href="..\sercx\nc-sercx-evt_sercx_purge.md">EvtSerCxPurge</a>



<a href="..\sercx\nc-sercx-evt_sercx_fileclose.md">EvtSerCxFileClose</a>



<a href="..\sercx\nc-sercx-evt_sercx_transmit.md">EvtSerCxTransmit</a>



<a href="..\sercx\nc-sercx-evt_sercx_apply_config.md">EvtSerCxApplyConfig</a>



<a href="..\sercx\nc-sercx-evt_sercx_receive.md">EvtSerCxReceive</a>



<a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a>



<a href="..\sercx\nc-sercx-evt_sercx_transmit_cancel.md">EvtSerCxTransmitCancel</a>



<a href="..\sercx\nf-sercx-sercx_config_init.md">SERCX_CONFIG_INIT</a>



<a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a>



<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetfilter.md">WdfFdoInitSetFilter</a>



<a href="..\sercx\nc-sercx-evt_sercx_fileopen.md">EvtSerCxFileOpen</a>



<a href="..\sercx\nc-sercx-evt_sercx_filecleanup.md">EvtSerCxFileCleanup</a>



<a href="..\sercx\nc-sercx-evt_sercx_waitmask.md">EvtSerCxWaitmask</a>



<a href="..\sercx\nc-sercx-evt_sercx_control.md">EvtSerCxControl</a>