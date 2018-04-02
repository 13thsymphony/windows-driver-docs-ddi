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
product:
- Windows
targetos: Windows
req.typenames: SERCX_CONFIG, *PSERCX_CONFIG
req.product: Windows 10 or later.
---

# _SERCX_CONFIG structure
The <b>SERCX_CONFIG</b> structure contains configuration information for the serial framework extension (SerCx).

## Syntax
```
typedef struct _SERCX_CONFIG {
  ULONG                     Size;
  WDF_TRI_STATE             PowerManaged;
  PFN_SERCX_FILEOPEN        EvtSerCxFileOpen;
  PFN_SERCX_FILECLOSE       EvtSerCxFileClose;
  PFN_SERCX_FILECLEANUP     EvtSerCxFileCleanup;
  PFN_SERCX_TRANSMIT        EvtSerCxTransmit;
  PFN_SERCX_RECEIVE         EvtSerCxReceive;
  PFN_SERCX_WAITMASK        EvtSerCxWaitmask;
  PFN_SERCX_PURGE           EvtSerCxPurge;
  PFN_SERCX_CONTROL         EvtSerCxControl;
  PFN_SERCX_APPLY_CONFIG    EvtSerCxApplyConfig;
  PFN_SERCX_TRANSMIT_CANCEL EvtSerCxTransmitCancel;
  PFN_SERCX_RECEIVE_CANCEL  EvtSerCxReceiveCancel;
} SERCX_CONFIG, *PSERCX_CONFIG;
```

## Members


`Size`

The size, in bytes, of this structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.

`PowerManaged`

Whether the controller queue should be power-managed. If set to <b>WdfTrue</b>, the controller queue should be power-managed.  If set to <b>WdfFalse</b>, the controller queue not be power-managed. If set to <b>WdfDefault</b>, the controller queue should be power-managed unless the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547273">WdfFdoInitSetFilter</a> method. For more information, see the description of the <b>PowerManaged</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/ff552359">WDF_IO_QUEUE_CONFIG</a>.

`EvtSerCxFileOpen`

A pointer to the controller driver's <a href="https://msdn.microsoft.com/90D08857-69E0-4DD9-9588-86900466E8DE">EvtSerCxFileOpen</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxFileClose`

A pointer to the controller driver's <a href="https://msdn.microsoft.com/C72CA6D0-DD85-46AC-9CE3-BE11233475C0">EvtSerCxFileClose</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxFileCleanup`

A pointer to the controller driver's <a href="https://msdn.microsoft.com/D9E19BD1-2C44-4F86-9AEB-F50443FAE8DC">EvtSerCxFileCleanup</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxTransmit`

A pointer to the controller driver's <a href="https://msdn.microsoft.com/B32335E4-3BDF-4161-9BE2-CF3557D76988">EvtSerCxTransmit</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxReceive`

A pointer to the controller driver's <a href="https://msdn.microsoft.com/C862D632-5425-4EEB-9C5D-BC3721D9F132">EvtSerCxReceive</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxWaitmask`

A pointer to the controller driver's <a href="https://msdn.microsoft.com/41F60807-5A00-4B0E-A57D-70D25C73F575">EvtSerCxWaitmask</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxPurge`

A pointer to the controller driver's <a href="https://msdn.microsoft.com/036D9AAC-C740-4108-B952-0A4F91585488">EvtSerCxPurge</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxControl`

A pointer to the controller driver's <a href="https://msdn.microsoft.com/2A88BA68-48A7-4C00-8031-CCC50A0C090D">EvtSerCxControl</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxApplyConfig`

A pointer to the controller driver's <a href="https://msdn.microsoft.com/DC0AB4E3-AA73-4DD5-B91D-95F9D3792321">EvtSerCxApplyConfig</a> callback function. This member is required to point to a valid callback function.

`EvtSerCxTransmitCancel`

A pointer to the controller driver's <a href="https://msdn.microsoft.com/7922A3BD-8829-42A3-9F94-3C26F1262626">EvtSerCxTransmitCancel</a> callback function. This member is optional and can be set to NULL.

`EvtSerCxReceiveCancel`

A pointer to the controller driver's <a href="https://msdn.microsoft.com/17362701-67C9-4275-B072-CB17111A838F">EvtSerCxReceiveCancel</a> callback function. This member is optional and can be set to NULL.

## Remarks
Before this structure is passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a> method, it must be initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439553">SERCX_CONFIG_INIT</a> function, and then modified by the controller driver to set the callback function pointers and the <b>PowerManaged</b> member.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | sercx.h |

## See Also

<a href="https://msdn.microsoft.com/DC0AB4E3-AA73-4DD5-B91D-95F9D3792321">EvtSerCxApplyConfig</a>



<a href="https://msdn.microsoft.com/2A88BA68-48A7-4C00-8031-CCC50A0C090D">EvtSerCxControl</a>



<a href="https://msdn.microsoft.com/D9E19BD1-2C44-4F86-9AEB-F50443FAE8DC">EvtSerCxFileCleanup</a>



<a href="https://msdn.microsoft.com/C72CA6D0-DD85-46AC-9CE3-BE11233475C0">EvtSerCxFileClose</a>



<a href="https://msdn.microsoft.com/90D08857-69E0-4DD9-9588-86900466E8DE">EvtSerCxFileOpen</a>



<a href="https://msdn.microsoft.com/036D9AAC-C740-4108-B952-0A4F91585488">EvtSerCxPurge</a>



<a href="https://msdn.microsoft.com/C862D632-5425-4EEB-9C5D-BC3721D9F132">EvtSerCxReceive</a>



<a href="https://msdn.microsoft.com/17362701-67C9-4275-B072-CB17111A838F">EvtSerCxReceiveCancel</a>



<a href="https://msdn.microsoft.com/B32335E4-3BDF-4161-9BE2-CF3557D76988">EvtSerCxTransmit</a>



<a href="https://msdn.microsoft.com/7922A3BD-8829-42A3-9F94-3C26F1262626">EvtSerCxTransmitCancel</a>



<a href="https://msdn.microsoft.com/41F60807-5A00-4B0E-A57D-70D25C73F575">EvtSerCxWaitmask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439553">SERCX_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552359">WDF_IO_QUEUE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547273">WdfFdoInitSetFilter</a>