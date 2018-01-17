---
UID: NS:wwan._WWAN_SERVICE_ACTIVATION
title: _WWAN_SERVICE_ACTIVATION
author: windows-driver-content
description: The WWAN_SERVICE_ACTIVATION structure represents a vendor-specific buffer to be associated with service activation.
old-location: netvista\wwan_service_activation.htm
old-project: netvista
ms.assetid: 1893a929-c9e6-446e-a840-3825f4992c18
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WWAN_SERVICE_ACTIVATION, WWAN_SERVICE_ACTIVATION, *PWWAN_SERVICE_ACTIVATION
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
req.alt-api: WWAN_SERVICE_ACTIVATION
req.alt-loc: wwan.h
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
req.typenames: WWAN_SERVICE_ACTIVATION, *PWWAN_SERVICE_ACTIVATION
req.product: Windows 10 or later.
---

# _WWAN_SERVICE_ACTIVATION structure



## -description
The WWAN_SERVICE_ACTIVATION structure represents a vendor-specific buffer to be associated with
  service activation.



## -syntax

````
typedef struct _WWAN_SERVICE_ACTIVATION {
  ULONG uVendorSpecificBufferSize;
} WWAN_SERVICE_ACTIVATION, *PWWAN_SERVICE_ACTIVATION;
````


## -struct-fields

### -field uVendorSpecificBufferSize

The size, in bytes, of the vendor-specific buffer that follows the structure instance in
     memory.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_service_activation.md">NDIS_WWAN_SERVICE_ACTIVATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SERVICE_ACTIVATION structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

