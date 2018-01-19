---
UID : NS:bthioctl._BTH_VENDOR_EVENT_INFO
title : _BTH_VENDOR_EVENT_INFO
author : windows-driver-content
description : The BTH_VENDOR_EVENT_INFO structure specifies the buffer that is associated with the GUID_BLUETOOTH_HCI_VENDOR_EVENT GUID.
old-location : bltooth\bth_vendor_event_info.htm
old-project : bltooth
ms.assetid : 796f9d91-5c75-4a05-a997-0d5beb7d9fca
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : _BTH_VENDOR_EVENT_INFO, *PBTH_VENDOR_EVENT_INFO, BTH_VENDOR_EVENT_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bthioctl.h
req.include-header : Bthioctl.h
req.target-type : Windows
req.target-min-winverclnt : Versions: Available in Windows Vista, and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BTH_VENDOR_EVENT_INFO
req.alt-loc : bthioctl.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= PASSIVE_LEVEL
req.typenames : "*PBTH_VENDOR_EVENT_INFO, BTH_VENDOR_EVENT_INFO"
---

# _BTH_VENDOR_EVENT_INFO structure
The BTH_VENDOR_EVENT_INFO structure specifies the buffer that is associated with the
  GUID_BLUETOOTH_HCI_VENDOR_EVENT GUID.

## Syntax
````
typedef struct _BTH_VENDOR_EVENT_INFO {
  BTH_ADDR BthAddress;
  ULONG    EventSize;
  UCHAR    EventInfo[1];
} BTH_VENDOR_EVENT_INFO, *PBTH_VENDOR_EVENT_INFO;
````

## Members

        
            `BthAddress`

            The address of the local radio that is associated with the event.
        
            `EventInfo`

            A UCHAR array for the event buffer. The buffer includes the event header.
        
            `EventSize`

            The size, in bytes, of the event buffer. The size includes the event header.

    ## Remarks
        The BTH_VENDOR_EVENT_INFO structure contains data that is associated with a
    GUID_BLUETOOTH_HCI_VENDOR_EVENT event.

An application or driver that registers for notifications for the GUID_BTHPORT_DEVICE_INTERFACE GUID
    receives the WM_DEVICECHANGE message that has 
    <i>wParam</i> set to DBT_CUSTOMEVENT and the event GUID set to GUID_BLUETOOTH_HCI_VENDOR_EVENT.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthioctl.h (include Bthioctl.h) |