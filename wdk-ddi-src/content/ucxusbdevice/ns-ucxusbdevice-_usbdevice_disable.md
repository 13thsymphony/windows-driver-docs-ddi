---
UID: NS:ucxusbdevice._USBDEVICE_DISABLE
title: "_USBDEVICE_DISABLE"
author: windows-driver-content
description: Contains parameters for a request to disable the specified device. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_DISABLE callback function.
old-location: buses\_usbdevice_disable.htm
old-project: usbref
ms.assetid: C9F2331F-0C16-47F3-9FDE-2719E179513F
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: USBDEVICE_DISABLE structure [Buses], buses._usbdevice_disable, P_USBDEVICE_DISABLE structure pointer [Buses], ucxusbdevice/_USBDEVICE_DISABLE, USBDEVICE_DISABLE, *PUSBDEVICE_DISABLE, ucxusbdevice/P_USBDEVICE_DISABLE, _USBDEVICE_DISABLE, P_USBDEVICE_DISABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxusbdevice.h
apiname:
-	USBDEVICE_DISABLE
product: Windows
targetos: Windows
req.typenames: "*PUSBDEVICE_DISABLE, USBDEVICE_DISABLE"
req.product: Windows 10 or later.
---

# _USBDEVICE_DISABLE structure
Contains parameters for a request to disable the specified device. This structure is passed by UCX in request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_disable.md">EVT_UCX_USBDEVICE_DISABLE</a> callback function.

## Syntax
````
typedef struct _USBDEVICE_DISABLE {
#if __cplusplus
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
  UCXENDPOINT           DefaultEndpoint;
} USBDEVICE_DISABLE, *P_USBDEVICE_DISABLE;
````

## Members


`DefaultEndpoint`

A handle to the default endpoint of the USB device or hub to disable.

`Header`

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |

## See Also

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_enable.md">USBDEVICE_ENABLE</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>



<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_disable.md">EVT_UCX_USBDEVICE_DISABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBDEVICE_DISABLE structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>