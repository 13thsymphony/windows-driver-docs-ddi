---
UID : NS:pointofservicedriverinterface._MSR_AUTHENTICATE_DEVICE
title : _MSR_AUTHENTICATE_DEVICE
author : windows-driver-content
description : This structure provides the authentication information used to authenticate a device.
old-location : pos\msr_authenticate_device.htm
old-project : pos
ms.assetid : b75dce2c-5ad5-4340-b1b7-5fcf4440e58c
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _MSR_AUTHENTICATE_DEVICE, *PMSR_AUTHENTICATE_DEVICE, MSR_AUTHENTICATE_DEVICE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : pointofservicedriverinterface.h
req.include-header : PointOfServiceDriverInterface.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : MSR_AUTHENTICATE_DEVICE
req.alt-loc : PointOfServiceDriverInterface.h
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
req.typenames : "*PMSR_AUTHENTICATE_DEVICE, MSR_AUTHENTICATE_DEVICE"
---

# _MSR_AUTHENTICATE_DEVICE structure
This structure provides the authentication information used to authenticate a device.

## Syntax
````
typedef struct _MSR_AUTHENTICATE_DEVICE {
   unsigned char Size;
  unsigned char  Challenge1;
  unsigned char  SessionId;
} MSR_AUTHENTICATE_DEVICE, *PMSR_AUTHENTICATE_DEVICE;
````

## Members

        
            `Challenge1`

            The challenge token.
        
            `SessionId`

            The session ID. This is primarily used to identify each transaction so that you can prevent errors such as processing the same transaction twice.
        
            `Size`

            If the optional <b>SessionId</b> is present, this will include the size of <b>SessionId[MSR_SESSION_ID_SIZE]</b>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |

    ## See Also

        <dl>
<dt>
<a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_msr_authenticate_device.md">IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20MSR_AUTHENTICATE_DEVICE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>