---
UID: NF:ks.KsCreatePin2
title: KsCreatePin2 function
author: windows-driver-content
description: Passes a connection request to a device, creating a pin instance.
old-location: stream\kscreatepin2.htm
old-project: stream
ms.assetid: 43408247-0c34-46bd-a36b-b11540a10c55
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsCreatePin2, KsCreatePin2 function [Streaming Media Devices], ks/KsCreatePin2, stream.kscreatepin2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ks.h
api_name:
-	KsCreatePin2
product: Windows
targetos: Windows
req.typenames: 
---


# KsCreatePin2 function
Passes a connection request to a device, creating a pin instance.

Supported starting in Windows 8.

## Syntax

````
KSDDKAPI HRESULT WINAPI KsCreatePin2(
  _In_  HANDLE         FilterHandle,
  _In_  PKSPIN_CONNECT Connect,
  _In_  ACCESS_MASK    DesiredAccess,
  _Out_ PHANDLE        ConnectionHandle
);
````

## Parameters

`FilterHandle`

Specifies the handle of the filter initiating the create request and where the connection will occur.

`Connect`

Pointer to a <a href="..\ks\ns-ks-kspin_connect.md">KSPIN_CONNECT</a> structure that contains parameters for the requested connection. This should be followed in memory by a <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a> data structure, describing the data format requested for the connection.

`DesiredAccess`

Specifies the access desired to the pin. This is typically <b>GENERIC_READ</b> or <b>GENERIC_WRITE</b>. For data flowing into the pin this value should be set to <b>GENERIC_WRITE</b>, and for data flowing out of the pin this should be set to <b>GENERIC_READ</b> regardless of the communication method.

`ConnectionHandle`

Specifies the connection handle passed. The routine fills this in with a handle to the file object of the created connection. This value can then be used to disconnect with the <a href="https://msdn.microsoft.com/9b84891d-62ca-4ddc-97b7-c4c79482abd9">CloseHandle</a> function.


## Return Value

Returns <b>NOERROR</b> if successful; otherwise, returns an error code.

## Remarks

This is a new version of the <a href="..\ks\nf-ks-kscreatepin.md">KsCreatePin</a> function and uses the device broker to create the handle to the kernel streaming object. In addition, the Component Object Model (COM) <a href="https://msdn.microsoft.com/0f171cf4-87b9-43a6-97f2-80ed344fe376">CoInitialize</a> function must be called before this function is called.

The routine sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request to the driver. The driver accepts the request only if the interface, medium, and data format are compatible.

If <i>Connect</i>-&gt;<b>PinToHandle</b> is <b>NULL</b>, <b>KsCreatePin2</b> creates a pin that the caller can use to send requests to the streaming driver specified in <i>Connect</i>-&gt;<b>FilterHandle</b>. <i>Connect</i>-&gt;<b>PinId</b> determines the type of pin to be created.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/0f171cf4-87b9-43a6-97f2-80ed344fe376">CoInitialize</a>



<a href="..\ks\nf-ks-kscreatepin.md">KsCreatePin</a>



<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>



<a href="..\ks\ns-ks-kspin_connect.md">KSPIN_CONNECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCreatePin2 function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>