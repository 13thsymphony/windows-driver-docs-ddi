---
UID : NI:ks.IOCTL_KS_HANDSHAKE
title : IOCTL_KS_HANDSHAKE
author : windows-driver-content
description : A kernel-mode client can use IOCTL_KS_HANDSHAKE to negotiate an interface between unconnected AVStream pins.
old-location : stream\ioctl_ks_handshake.htm
old-project : stream
ms.assetid : 63c50af0-365b-4074-a703-9e43b1514a55
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.ioctl_ks_handshake, IOCTL_KS_HANDSHAKE control code [Streaming Media Devices], IOCTL_KS_HANDSHAKE, ks/IOCTL_KS_HANDSHAKE, ks-ioctl_f848d65c-b795-439e-a8a1-d4c2e0764ef1.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ks.h
req.include-header : Ks.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---

# IOCTL_KS_HANDSHAKE IOCTL
A kernel-mode client can use IOCTL_KS_HANDSHAKE to negotiate an interface between unconnected AVStream pins. The client calls <a href="..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md">KsSynchronousDeviceControl</a> with IOCTL_KS_HANDSHAKE and the parameters described below.

To attempt a protocol handshake with a pin that is already connected, call <a href="..\ks\nf-ks-kspinhandshake.md">KsPinHandshake</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The client places a pointer to a structure of type <a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a> in the <b>InBuffer</b> parameter.

### Input Buffer Length
<b>InLength </b>must be equal to sizeof(KSHANDSHAKE).

### Output Buffer
The client places a pointer to a structure of type <a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a> in the <b>OutBuffer</b> parameter. If the request is successful, handshake information is placed in this location.

### Output Buffer Length
<b>OutLength </b>must be equal to sizeof(KSHANDSHAKE).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, IoStatus.Information is set to sizeof(KSHANDSHAKE).

This IOCTL can be sent from kernel-mode only. If the request is sent from user mode, the Status member is set to STATUS_INVALID_DEVICE_REQUEST. 

If the <b>InLength</b> and <b>OutLength</b> parameters in the call to <b>KsSynchronousDeviceControl</b> are not both equal to sizeof(KSHANDSHAKE), the Status member is set to STATUS_INVALID_BUFFER_SIZE.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ks.h (include Ks.h) |
| **IRQL** |  |

## See Also

<a href="..\ks\nf-ks-kspinhandshake.md">KsPinHandshake</a>

<a href="..\ks\nc-ks-pfnkspinhandshake.md">AVStrMiniPinHandshake</a>

<a href="..\ks\nf-ks-kspinregisterhandshakecallback.md">KsPinRegisterHandshakeCallback</a>

<a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IOCTL_KS_HANDSHAKE control code%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>