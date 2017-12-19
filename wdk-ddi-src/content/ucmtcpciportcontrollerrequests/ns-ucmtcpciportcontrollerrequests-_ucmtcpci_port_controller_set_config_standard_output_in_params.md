---
UID: NS.UCMTCPCIPORTCONTROLLERREQUESTS._UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS
title: _UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS
author: windows-driver-content
description: Stores the value of the CONFIG_STANDARD_OUTPUT Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT request.
old-location: buses\ucmtcpci_port_controller_set_config_standard_output_in_params.htm
old-project: UsbRef
ms.assetid: 86db9434-b3df-4598-866f-db3e8957aeec
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS
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
req.alt-api: UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS
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
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS structure



## -description
Stores the value of the CONFIG_STANDARD_OUTPUT Register. 
                 This structure is used in the <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_config_standard_output.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT</a> request.
             



## -syntax

````
typedef struct _UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER                          PortControllerObject;
  UCMTCPCI_PORT_CONTROLLER_CONFIG_STANDARD_OUTPUT ConfigStandardOutput;
} UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS;
````


## -struct-fields

### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="buses.ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>.


### -field ConfigStandardOutput


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_CONFIG_STANDARD_OUTPUT</b> structure that describes the CONFIG_STANDARD_OUTPUT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_config_standard_output.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

