---
UID: NS:wwan._WWAN_SERVICE_ACTIVATION
title: "_WWAN_SERVICE_ACTIVATION"
author: windows-driver-content
description: The WWAN_SERVICE_ACTIVATION structure represents a vendor-specific buffer to be associated with service activation.
old-location: netvista\wwan_service_activation.htm
old-project: netvista
ms.assetid: 1893a929-c9e6-446e-a840-3825f4992c18
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WWAN_SERVICE_ACTIVATION structure [Network Drivers Starting with Windows Vista], wwan/PWWAN_SERVICE_ACTIVATION, *PWWAN_SERVICE_ACTIVATION, PWWAN_SERVICE_ACTIVATION structure pointer [Network Drivers Starting with Windows Vista], PWWAN_SERVICE_ACTIVATION, WWAN_SERVICE_ACTIVATION, WwanRef_90dec032-ce8e-4b19-a4d8-e9a7a22d681e.xml, _WWAN_SERVICE_ACTIVATION, wwan/WWAN_SERVICE_ACTIVATION, netvista.wwan_service_activation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	wwan.h
apiname:
-	WWAN_SERVICE_ACTIVATION
product: Windows
targetos: Windows
req.typenames: WWAN_SERVICE_ACTIVATION, *PWWAN_SERVICE_ACTIVATION
req.product: Windows 10 or later.
---

# _WWAN_SERVICE_ACTIVATION structure
The WWAN_SERVICE_ACTIVATION structure represents a vendor-specific buffer to be associated with
  service activation.

## Syntax
````
typedef struct _WWAN_SERVICE_ACTIVATION {
  ULONG uVendorSpecificBufferSize;
} WWAN_SERVICE_ACTIVATION, *PWWAN_SERVICE_ACTIVATION;
````

## Members


`uVendorSpecificBufferSize`

The size, in bytes, of the vendor-specific buffer that follows the structure instance in
     memory.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_service_activation.md">NDIS_WWAN_SERVICE_ACTIVATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SERVICE_ACTIVATION structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>