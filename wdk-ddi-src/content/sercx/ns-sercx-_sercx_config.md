---
UID : NS:sercx._SERCX_CONFIG
title : _SERCX_CONFIG
author : windows-driver-content
description : The SERCX_CONFIG structure contains configuration information for the serial framework extension (SerCx).
old-location : serports\sercx_config.htm
old-project : serports
ms.assetid : 2CBCBA07-C489-4475-A856-8748FBFDC141
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SERCX_CONFIG, PSERCX_CONFIG, serports.sercx_config, 1/PSERCX_CONFIG, SERCX_CONFIG structure [Serial Ports], _SERCX_CONFIG, PSERCX_CONFIG structure pointer [Serial Ports], 1/SERCX_CONFIG, *PSERCX_CONFIG
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : sercx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Any IRQL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SERCX_CONFIG, *PSERCX_CONFIG
req.product : Windows 10 or later.
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


`EvtSerCxApplyConfig`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_apply_config.md">EvtSerCxApplyConfig</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxControl`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_control.md">EvtSerCxControl</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxFileCleanup`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_filecleanup.md">EvtSerCxFileCleanup</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxFileClose`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_fileclose.md">EvtSerCxFileClose</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxFileOpen`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_fileopen.md">EvtSerCxFileOpen</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxPurge`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_purge.md">EvtSerCxPurge</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxReceive`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_receive.md">EvtSerCxReceive</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxReceiveCancel`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_receive_cancel.md">EvtSerCxReceiveCancel</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxTransmit`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_transmit.md">EvtSerCxTransmit</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxTransmitCancel`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_transmit_cancel.md">EvtSerCxTransmitCancel</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxWaitmask`

A pointer to the controller driver's <a href="..\sercx\nc-sercx-evt_sercx_waitmask.md">EvtSerCxWaitmask</a> callback function. This member is required to point to a valid callback function.

`PowerManaged`

Whether the controller queue should be power-managed. If set to <b>WdfTrue</b>, the controller queue should be power-managed.  If set to <b>WdfFalse</b>, the controller queue not be power-managed. If set to <b>WdfDefault</b>, the controller queue should be power-managed unless the driver calls the <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetfilter.md">WdfFdoInitSetFilter</a> method. For more information, see the description of the <b>PowerManaged</b> member in <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a>.

`Size`

The size, in bytes, of this structure. The <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.

## Remarks
Before this structure is passed to the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method, it must be initialized by the <a href="..\sercx\nf-sercx-sercx_config_init.md">SERCX_CONFIG_INIT</a> function, and then modified by the controller driver to set the callback function pointers and the <b>PowerManaged</b> member.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sercx.h |

## See Also

<a href="..\sercx\nc-sercx-evt_sercx_fileclose.md">EvtSerCxFileClose</a>

<a href="..\sercx\nc-sercx-evt_sercx_receive.md">EvtSerCxReceive</a>

<a href="..\sercx\nc-sercx-evt_sercx_receive_cancel.md">EvtSerCxReceiveCancel</a>

<a href="..\sercx\nc-sercx-evt_sercx_control.md">EvtSerCxControl</a>

<a href="..\sercx\nc-sercx-evt_sercx_apply_config.md">EvtSerCxApplyConfig</a>

<a href="..\sercx\nc-sercx-evt_sercx_filecleanup.md">EvtSerCxFileCleanup</a>

<a href="..\sercx\nc-sercx-evt_sercx_transmit.md">EvtSerCxTransmit</a>

<a href="..\sercx\nc-sercx-evt_sercx_waitmask.md">EvtSerCxWaitmask</a>

<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetfilter.md">WdfFdoInitSetFilter</a>

<a href="..\sercx\nc-sercx-evt_sercx_purge.md">EvtSerCxPurge</a>

<a href="..\sercx\nc-sercx-evt_sercx_transmit_cancel.md">EvtSerCxTransmitCancel</a>

<a href="..\sercx\nc-sercx-evt_sercx_fileopen.md">EvtSerCxFileOpen</a>

<a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a>

<a href="..\sercx\nf-sercx-sercx_config_init.md">SERCX_CONFIG_INIT</a>

<a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX_CONFIG structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>