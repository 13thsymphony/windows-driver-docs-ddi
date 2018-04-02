---
UID: NS:bthddi._BTH_ENUMERATOR_INFO
title: "_BTH_ENUMERATOR_INFO"
author: windows-driver-content
description: The BTH_ENUMERATOR_INFO structure contains information about an underlying device and the service that caused the Plug and Play (PnP) manager to load the profile driver.
old-location: bltooth\bth_enumerator_info.htm
old-project: bltooth
ms.assetid: e526d664-35cf-4738-9501-08298e90be1e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBTH_ENUMERATOR_INFO, BTH_ENUMERATOR_INFO, BTH_ENUMERATOR_INFO structure [Bluetooth Devices], PBTH_ENUMERATOR_INFO, PBTH_ENUMERATOR_INFO structure pointer [Bluetooth Devices], _BTH_ENUMERATOR_INFO, bltooth.bth_enumerator_info, bth_structs_7cdc888a-ed42-4988-917f-578522399179.xml, bthddi/BTH_ENUMERATOR_INFO, bthddi/PBTH_ENUMERATOR_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	BTH_ENUMERATOR_INFO
product: Windows
targetos: Windows
req.typenames: BTH_ENUMERATOR_INFO, *PBTH_ENUMERATOR_INFO
---

# _BTH_ENUMERATOR_INFO structure
The BTH_ENUMERATOR_INFO structure contains information about an underlying device and the service
  that caused the Plug and Play (PnP) manager to load the profile driver.

## Syntax
```
typedef struct _BTH_ENUMERATOR_INFO {
  ENUMERATOR_TYPE   EnumeratorType;
  ENUMERATOR_ACTION Action;
  ULONG             Port;
  ULONG             Flags;
  GUID              Guid;
  ULONG             InstanceId;
  WCHAR             InstanceIdStr[BTH_MAX_SERVICE_NAME_SIZE];
  USHORT            Vid;
  USHORT            Pid;
  USHORT            Mfg;
  USHORT            LocalMfg;
  USHORT            VidType;
  WCHAR             ServiceName[BTH_MAX_SERVICE_NAME_SIZE];
  CHAR              SdpPriLangServiceName[BTH_MAX_SERVICE_NAME_SIZE];
  WCHAR             DeviceString[BTH_MAX_SERVICE_NAME_SIZE];
} *PBTH_ENUMERATOR_INFO, BTH_ENUMERATOR_INFO;
```

## Members


`EnumeratorType`

Reserved for use by the Bluetooth driver stack. Do not use.

`Action`

Reserved for use by the Bluetooth driver stack. Do not use.

`Port`

If the enumeration was caused by a connection request, this member contains the device's port
     number. Otherwise, this value is undefined. For a L2CAP connection request, the port number also
     identifies the Protocol/Service Multiplexer (PSM) that is being connected to. For an RFCOMM connection
     request, this is an RFCOMM data link connection identifier (DLCI).

`Flags`

A flag that indicates the direction of the request. Possible values include:

<ul>
<li>BTH_ENUMERATORFL_INCOMING</li>
<li>BTH_ENUMERATORFL_OUTGOING</li>
<li>BTH_ENUMERATORFL_REENUM</li>
</ul>

`Guid`

The enumeration protocol or service class GUID. This value is usually obtained from the INF file
      that loaded the profile driver.

`InstanceId`

The instance ID of the protocol or service if the BTH_ENUMERATORFL_INCOMING flag is set.

`InstanceIdStr`

The instance ID of the protocol or service if the BTH_ENUMERATORFL_OUTGOING flag is set.

`Vid`

The vendor ID of the remote device, which is obtained from SDP.

`Pid`

The product ID of the remote device, which is obtained from SDP.

`Mfg`

The manufacturer ID of the remote device, which is obtained from SDP.

`LocalMfg`

The local radio manufacturer obtained from the HCI.

`VidType`

The remote device vendor ID type, which is obtained from SDP.

`ServiceName`

The service name that is used for local services.

`SdpPriLangServiceName`

The identifier used for remote services.

`DeviceString`

The device string for the remote device.

## Remarks
The 
    <a href="https://msdn.microsoft.com/43cd8e6b-5710-4308-a7c4-fb6f14940977">
    IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO</a> call's output buffer contains the information about an
    underlying device and the service that caused the Plug and Play (PnP) manager to load the profile
    driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="https://msdn.microsoft.com/d5acaec6-7b3b-4dd9-8901-f96b4e49149f">ENUMERATOR_ACTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536678">ENUMERATOR_TYPE</a>



<a href="https://msdn.microsoft.com/43cd8e6b-5710-4308-a7c4-fb6f14940977">
   IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO</a>