---
UID : NS:bthioctl._BTH_LOCAL_RADIO_INFO
title : _BTH_LOCAL_RADIO_INFO
author : windows-driver-content
description : The BTH_LOCAL_RADIO_INFO structure contains information about the local Bluetooth system and radio.
old-location : bltooth\bth_local_radio_info.htm
old-project : bltooth
ms.assetid : 288863ca-1a11-456f-8d6b-b429668c2bf2
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : _BTH_LOCAL_RADIO_INFO, BTH_LOCAL_RADIO_INFO, *PBTH_LOCAL_RADIO_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bthioctl.h
req.include-header : Bthioctl.h
req.target-type : Windows
req.target-min-winverclnt : Supported in Windows Vista, and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BTH_LOCAL_RADIO_INFO
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
req.typenames : BTH_LOCAL_RADIO_INFO, *PBTH_LOCAL_RADIO_INFO
---

# _BTH_LOCAL_RADIO_INFO structure
The BTH_LOCAL_RADIO_INFO structure contains information about the local Bluetooth system and
  radio.

## Syntax
````
typedef struct _BTH_LOCAL_RADIO_INFO {
  BTH_DEVICE_INFO localInfo;
  ULONG           flags;
  USHORT          hciRevision;
  UCHAR           hciVersion;
  BTH_RADIO_INFO  radioInfo;
} BTH_LOCAL_RADIO_INFO, *PBTH_LOCAL_RADIO_INFO;
````

## Members

        
            `flags`

            A flag that indicates the state of the local radio. Both flags can be set at the same time.
     Possible values include:
     

<dl>
<dd>
LOCAL_RADIO_DISCOVERABLE

</dd>
<dd>




</dd>
<dd>
LOCAL_RADIO_CONNECTABLE

</dd>
</dl>
        
            `hciRevision`

            The minor version of the host controller interface (HCI).
        
            `hciVersion`

            The major version of the HCI.
        
            `localInfo`

            A 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structure that contains
     information about the local radio.
        
            `radioInfo`

            A 
     <a href="..\bthioctl\ns-bthioctl-_bth_radio_info.md">BTH_RADIO_INFO</a> structure that contains
     information about the local radio device.

    ## Remarks
        The 
    <a href="..\bthioctl\ni-bthioctl-ioctl_bth_get_local_info.md">IOCTL_BTH_GET_LOCAL_INFO</a> call's
    output buffer contains the information about the local Bluetooth system and radio.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthioctl.h (include Bthioctl.h) |

    ## See Also

        <dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a></dt>
<dt>
<a href="..\bthioctl\ns-bthioctl-_bth_radio_info.md">BTH_RADIO_INFO</a>
</dt>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_get_local_info.md">IOCTL_BTH_GET_LOCAL_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_LOCAL_RADIO_INFO structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>