---
UID: NS.UCMTCPCIPORTCONTROLLER._UCMTCPCI_PORT_CONTROLLER_CONFIG
title: _UCMTCPCI_PORT_CONTROLLER_CONFIG
author: windows-driver-content
description: Contains configuration options for the port controller object, passed by the client driver in the call to UcmTcpciPortControllerCreate. Call UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT to initialize this structure.
old-location: buses\ucmtcpci_port_controller_config.htm
old-project: usbref
ms.assetid: a9027cda-0851-46e2-9006-0d757109fc3a
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UCMTCPCI_PORT_CONTROLLER_CONFIG, UCMTCPCI_PORT_CONTROLLER_CONFIG, *PUCMTCPCI_PORT_CONTROLLER_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmtcpciportcontroller.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCMTCPCI_PORT_CONTROLLER_CONFIG
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
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_CONFIG structure



## -description

                 Contains configuration options for the port controller object,  passed by the client driver in the call to <a href="buses.ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>. Call <a href="buses.ucmtcpci_port_controller_config_init">UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT</a> to initialize this structure.
             



## -syntax

````
typedef struct _UCMTCPCI_PORT_CONTROLLER_CONFIG {
  ULONG                                    Size;
  PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION Identification;
  PUCMTCPCI_PORT_CONTROLLER_CAPABILITIES   Capabilities;
} UCMTCPCI_PORT_CONTROLLER_CONFIG, *PUCMTCPCI_PORT_CONTROLLER_CONFIG;
````


## -struct-fields

### -field Size


                     Size of this structure.
                 


### -field Identification

A pointer to the <a href="buses.ucmtcpci_port_controller_identification">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</a> structure.


### -field Capabilities

 A pointer to the 
                 <a href="buses.ucmtcpci_port_controller_capabilities">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES</a> structure.


## -remarks


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="buses.ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_CONFIG structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

