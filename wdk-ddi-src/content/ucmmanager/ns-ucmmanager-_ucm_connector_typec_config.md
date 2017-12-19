---
UID: NS.UCMMANAGER._UCM_CONNECTOR_TYPEC_CONFIG
title: _UCM_CONNECTOR_TYPEC_CONFIG
author: windows-driver-content
description: Describes the configuration options for a Type-C connector.
old-location: buses\ucm_connector_type_c_config.htm
old-project: UsbRef
ms.assetid: F3C17CD8-F423-46E7-891F-E428235CEF3D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _UCM_CONNECTOR_TYPEC_CONFIG, PUCM_CONNECTOR_TYPEC_CONFIG, UCM_CONNECTOR_TYPEC_CONFIG, *PUCM_CONNECTOR_TYPEC_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.alt-api: UCM_CONNECTOR_TYPEC_CONFIG
req.alt-loc: Ucmmanager.h
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

# _UCM_CONNECTOR_TYPEC_CONFIG structure



## -description
Describes the configuration options for a Type-C connector. 



## -syntax

````
typedef struct _UCM_CONNECTOR_TYPEC_CONFIG {
  ULONG                           Size;
  BOOLEAN                         IsSupported;
  ULONG                           SupportedOperatingModes;
  ULONG                           SupportedPowerSourcingCapabilities;
  BOOLEAN                         AudioAccessoryCapable;
  PFN_UCM_CONNECTOR_SET_DATA_ROLE EvtSetDataRole;
} UCM_CONNECTOR_TYPEC_CONFIG, *PUCM_CONNECTOR_TYPEC_CONFIG;
````


## -struct-fields

### -field Size

Size of the <b>UCM_CONNECTOR_TYPEC_CONFIG</b> structure. 


### -field IsSupported

TRUE indicates a Type-C connector. FALSE, otherwise.  is supported. 


### -field SupportedOperatingModes

Indicates the supported operating mode of the connector. This value is a bitwise OR of <a href="buses.ucm_type_c_operating_mode">UCM_TYPEC_OPERATING_MODE</a>-typed flags.


### -field SupportedPowerSourcingCapabilities

Indicates the supported power source capabilities of the connector. This value is a bitwise OR of <a href="buses.ucm_type_c_current">UCM_TYPEC_CURRENT</a>-typed flags.


### -field AudioAccessoryCapable

Indicates whether the connector is capable of detecting a USB Type-C analog input as 3.5 mm audio jack.


### -field EvtSetDataRole

A pointer to the client driver's implementation of the <a href="..\ucmmanager\nc-ucmmanager-evt_ucm_connector_set_data_role.md">EVT_UCM_CONNECTOR_SET_DATA_ROLE</a> callback function.


## -remarks
Initialize this structure by calling <a href="buses.ucm_connector_type_c_config_init">UCM_CONNECTOR_TYPEC_CONFIG_INIT</a>. An initialized <b>UCM_CONNECTOR_TYPEC_CONFIG</b> structure is an input parameter value to <a href="buses.ucmconnectorcreate">UcmConnectorCreate</a> that is used by Policy Manager to create a connector object.


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
Minimum KMDF version

</th>
<td width="70%">
1.15

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.15

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucmmanager.h (include Ucmcx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.ucmconnectorcreate">UcmConnectorCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCM_CONNECTOR_TYPEC_CONFIG structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
