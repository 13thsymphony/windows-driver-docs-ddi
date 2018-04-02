---
UID: NF:ks.KsCreatePin
title: KsCreatePin function
author: windows-driver-content
description: The KsCreatePin function passes a connection request to a device, creating a pin instance. This function can only be called at PASSIVE_LEVEL for kernel-mode clients.
old-location: stream\kscreatepin.htm
old-project: stream
ms.assetid: 0dae335a-bcc1-4f6a-8926-e2ecc4112dc5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsCreatePin, KsCreatePin function [Streaming Media Devices], ks/KsCreatePin, ksfunc_f49fab36-1309-4eec-addb-4eba94583692.xml, stream.kscreatepin
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	ks.lib
-	ks.dll
-	ksuser.dll
api_name:
-	KsCreatePin
product:
- Windows
targetos: Windows
req.typenames: 
---


# KsCreatePin function
The <b>KsCreatePin</b> function passes a connection request to a device, creating a pin instance. This function can only be called at <b>PASSIVE_LEVEL</b> for kernel-mode clients.

## Syntax

```
KSDDKAPI NTSTATUS KsCreatePin(
  HANDLE         FilterHandle,
  PKSPIN_CONNECT Connect,
  ACCESS_MASK    DesiredAccess,
  PHANDLE        ConnectionHandle
);
```

## Parameters

`FilterHandle`

Specifies the handle of the filter initiating the create request and where the connection will occur.

`Connect`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563531">KSPIN_CONNECT</a> structure that contains parameters for the requested connection. This should be followed in memory by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a> data structure, describing the data format requested for the connection.

`DesiredAccess`

Specifies the access desired to the pin. This is typically <b>GENERIC_READ</b> or <b>GENERIC_WRITE</b>. For data flowing into the pin this value should be set to <b>GENERIC_WRITE</b>, and for data flowing out of the pin this should be set to <b>GENERIC_READ</b> regardless of the communication method.

`ConnectionHandle`

Specifies the connection handle passed. The routine fills this in with a handle to the file object of the created connection. This value can then be used to disconnect with the <a href="https://msdn.microsoft.com/9b84891d-62ca-4ddc-97b7-c4c79482abd9">CloseHandle</a> function.


## Return Value

The <b>KsCreatePin</b> function returns <b>STATUS_SUCCESS</b> if the connection was successful, or it returns an error if the connection failed. Additionally, this Win32 error code (from Winerror.h) can be returned:

## Remarks

The routine sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request to the driver. The driver accepts the request only if the interface, medium, and data format are compatible.

If <i>Connect</i>-&gt;<b>PinToHandle</b> is <b>NULL</b>, <b>KsCreatePin</b> creates a pin the caller can use to send requests to the streaming driver specified in <i>Connect</i>-&gt;<b>FilterHandle</b>. <i>Connect</i>-&gt;<b>PinId</b> determines the pin type of the pin to be created.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563531">KSPIN_CONNECT</a>