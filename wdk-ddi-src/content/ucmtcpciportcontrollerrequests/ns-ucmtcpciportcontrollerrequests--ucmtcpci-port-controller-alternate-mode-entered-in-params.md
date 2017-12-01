---
UID: NS.ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS
title: UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS
author: windows-driver-content
description: Stores information about the alternate mode that was detected. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED request.
old-location: buses\ucmtcpci_port_controller_alternate_mode_entered_in_params.htm
old-project: usbref
ms.assetid: 526615F3-1019-4B84-97DA-BA56DC31A1F2
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmtcpciportcontrollerrequests.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS
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
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS structure



## -description
<p>Stores information about the  alternate mode that was detected. This structure is used in the 
             <a href="buses.ioctl_ucmtcpci_port_controller_alternate_mode_entered">IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED</a>  request. </p>


## -syntax

````
typedef struct _UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER PortControllerObject;
  UINT16                 SVID;
  UINT32                 Mode;
} UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS;
````


## -struct-fields
<dl>

### -field <b>PortControllerObject</b>

<dd>
<p>Handle to the port controller object that the client driver received in the previous call to <a href="buses.ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>.</p>
</dd>

### -field <b>SVID</b>

<dd>
<p>The Standard or Vendor ID (SVID) for the alternate mode that was entered. In Windows 10, version 1703, the supported  value is DISPLAYPORT_SVID, indicating that the partner device has entered DisplayPort mode. </p>
</dd>

### -field <b>Mode</b>

<dd>
<p>The Standard or Vendor defined Mode value for the alternate mode that was entered. </p>
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
<a href="buses.ioctl_ucmtcpci_port_controller_alternate_mode_entered">IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
