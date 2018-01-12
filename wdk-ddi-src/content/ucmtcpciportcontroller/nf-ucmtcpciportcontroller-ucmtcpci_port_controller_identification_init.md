---
UID: NF:ucmtcpciportcontroller.UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT
title: UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT function
author: windows-driver-content
description: Initializes the UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure.
old-location: buses\ucmtcpci_port_controller_identification_init.htm
old-project: usbref
ms.assetid: 4204b849-8195-4a1b-9bb3-1e9cbeb12223
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmtcpciportcontroller.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT
req.alt-loc: ucmtcpciportcontroller.h
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
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---

# UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT function



## -description

                        Initializes the <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_identification.md">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</a> structure.
                



## -syntax

````
VOID UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT(
  _Out_ PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION Identification
);
````


## -parameters

### -param Identification [out]

A pointer to the driver-allocated <b>UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</b> structure.


## -returns
This method does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucmtcpciportcontroller.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT method%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

