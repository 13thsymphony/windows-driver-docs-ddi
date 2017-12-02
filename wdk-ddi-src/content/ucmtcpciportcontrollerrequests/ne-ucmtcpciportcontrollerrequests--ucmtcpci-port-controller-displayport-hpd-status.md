---
UID: NE.ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS
title: UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS
author: windows-driver-content
description: Defines values to determine whether a DisplayPort device is plugged in.
old-location: buses\ucmtcpci_port_controller_displayport_hpd_status.htm
old-project: usbref
ms.assetid: 6BE5948B-DAC9-4448-AE22-108805BB364C
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, *PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtcpciportcontrollerrequests.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS
req.alt-loc: Ucmtcpciportcontrollerrequests.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS enumeration



## -description
<p>Defines values to determine whether a DisplayPort device is plugged in.</p>


## -syntax

````
typedef enum _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS { 
  UcmTcpciPortControllerHPDStatusLow   = 0x1,
  UcmTcpciPortControllerHPDStatusHigh  = 0x2
} UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS;
````


## -enum-fields
<dl>

### -field UcmTcpciPortControllerHPDStatusLow

<dd>
<p>The DisplayPort device is unplugged.</p>
</dd>

### -field UcmTcpciPortControllerHPDStatusHigh

<dd>
<p>A DisplayPort device such as a monitor is plugged in.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ucmtcpciportcontrollerrequests.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl-ucmtcpci-port-controller-displayport-hpd-status-changed.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS enumeration%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
