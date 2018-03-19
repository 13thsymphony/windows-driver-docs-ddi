---
UID: NS:nfccx._NFC_CX_CLIENT_CONFIG
title: "_NFC_CX_CLIENT_CONFIG"
author: windows-driver-content
description: The NFC_CX_CLIENT_CONFIG structure is an input parameter to NfcCxDeviceInitConfig.
old-location: nfpdrivers\nfc_cx_client_config.htm
old-project: nfpdrivers
ms.assetid: 8E005C77-4234-4B32-90F2-E4A8A7CD6305
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PNFC_CX_CLIENT_CONFIG, NFC_CX_CLIENT_CONFIG, NFC_CX_CLIENT_CONFIG structure [Near-Field Proximity Drivers], PNFC_CX_CLIENT_CONFIG, PNFC_CX_CLIENT_CONFIG structure pointer [Near-Field Proximity Drivers], _NFC_CX_CLIENT_CONFIG, nfccx/PNFC_CX_CLIENT_CONFIG, nfccx/_NFC_CX_CLIENT_CONFIG, nfpdrivers.nfc_cx_client_config"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	nfccx.h
api_name:
-	NFC_CX_CLIENT_CONFIG
product: Windows
targetos: Windows
req.typenames: NFC_CX_CLIENT_CONFIG, *PNFC_CX_CLIENT_CONFIG
---

# _NFC_CX_CLIENT_CONFIG structure
The NFC_CX_CLIENT_CONFIG structure is an input parameter to <a href="..\nfccx\nf-nfccx-nfccxdeviceinitconfig.md">NfcCxDeviceInitConfig</a>.

## Syntax
````
typedef struct _NFC_CX_CLIENT_CONFIG {
  ULONG                              Size;
  WDF_TRI_STATE                      IsPowerPolicyOwner;
  ULONG                              PowerIdleTimeout;
  WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE PowerIdleType;
  NFC_CX_TRANSPORT_TYPE              BusType;
  ULONG                              DriverFlags;
  NFC_CX_DEVICE_MODE                 DeviceMode;
  PFN_NFC_CX_WRITE_NCI_PACKET        EvtNfcCxWriteNciPacket;
  PFN_NFC_CX_DEVICE_IO_CONTROL       EvtNfcCxDeviceIoControl;
} NFC_CX_CLIENT_CONFIG, *PNFC_CX_CLIENT_CONFIG;
````

## Members


`Size`

Size of this structure in bytes.

`IsPowerPolicyOwner`

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed enumerator.

`PowerIdleTimeout`

IdleTimeout value, in milliseconds. Default is 1 second.

`PowerIdleType`

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_power_policy_idle_timeout_type.md">WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE</a>-typed enumerator.

`BusType`

An <a href="..\nfccx\ne-nfccx-_nfc_cx_transport_type.md">NFC_CX_TRANSPORT_TYPE</a>-typed enumerator.

`DriverFlags`

Combination of <a href="..\nfccx\ne-nfccx-_nfc_cx_driver_flags.md">NFC_CX_DRIVER_FLAGS</a> values.

`DeviceMode`

Device mode.

`EvtNfcCxWriteNciPacket`

Pointer to an <a href="..\nfccx\nc-nfccx-evt_nfc_cx_write_nci_packet.md">EvtNfcCxWriteNciPacket</a> callback.

`EvtNfcCxDeviceIoControl`

Pointer to an <a href="..\nfccx\nc-nfccx-evt_nfc_cx_device_io_control.md">EvtNfcCxDeviceIoControl</a> callback.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | nfccx.h (include Ncidef.h) |

## See Also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>