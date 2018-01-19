---
UID : NS:wwan._WWAN_DEVICE_SERVICE_SESSION_WRITE
title : _WWAN_DEVICE_SERVICE_SESSION_WRITE
author : windows-driver-content
description : The WWAN_DEVICE_SERVICE_SESSION_WRITE structure represents data associated with a device service session write request.
old-location : netvista\wwan_device_service_session_write.htm
old-project : netvista
ms.assetid : 8134E635-5FC3-4990-A7CC-E43ECEB1FBB6
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WWAN_DEVICE_SERVICE_SESSION_WRITE, WWAN_DEVICE_SERVICE_SESSION_WRITE, *PWWAN_DEVICE_SERVICE_SESSION_WRITE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wwan.h
req.include-header : Wwan.h
req.target-type : Windows
req.target-min-winverclnt : Supported starting with  Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : WWAN_DEVICE_SERVICE_SESSION_WRITE
req.alt-loc : wwan.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : WWAN_DEVICE_SERVICE_SESSION_WRITE, *PWWAN_DEVICE_SERVICE_SESSION_WRITE
req.product : Windows 10 or later.
---

# _WWAN_DEVICE_SERVICE_SESSION_WRITE structure
The WWAN_DEVICE_SERVICE_SESSION_WRITE structure represents data associated with a device service session write request.

## Syntax
````
typedef struct _WWAN_DEVICE_SERVICE_SESSION_WRITE {
  ULONG uSessionID;
  ULONG uDataSize;
} WWAN_DEVICE_SERVICE_SESSION_WRITE, *PWWAN_DEVICE_SERVICE_SESSION_WRITE;
````

## Members

        
            `uDataSize`

            The size, in bytes, of the device service data that follows the structure instance in memory. This value should not exceed the value of the <b>uMaxSessionDataSize</b> member of the <a href="..\wwan\ns-wwan-_wwan_supported_device_services.md">WWAN_SUPPORTED_DEVICE_SERVICES</a> structure.
        
            `uSessionID`

            The session ID of the device service.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wwan.h (include Wwan.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_device_service_session_write.md">NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan-_wwan_supported_device_services.md">WWAN_SUPPORTED_DEVICE_SERVICES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_DEVICE_SERVICE_SESSION_WRITE structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>