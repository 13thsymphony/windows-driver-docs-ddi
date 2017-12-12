---
UID: NS.HBAPIWMI._SENDRPL_IN
title: _SendRPL_IN
author: windows-driver-content
description: The SendRPL_IN structure is used to deliver input parameter data to the SendRPL WMI method.
old-location: storage\sendrpl_in.htm
old-project: storage
ms.assetid: 0c084258-2bd6-47a8-a060-d4ba2734ebed
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SendRPL_IN, *PSendRPL_IN, SendRPL_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SendRPL_IN
req.alt-loc: hbapiwmi.h
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
---

# _SendRPL_IN structure



## -description
The SendRPL_IN structure is used to deliver input parameter data to the <a href="storage.sendrpl">SendRPL</a> WMI method.



## -syntax

````
typedef struct _SendRPL_IN {
  UCHAR PortWWN[8];
  UCHAR AgentWWN[8];
  ULONG agent_domain;
  ULONG portIndex;
} SendRPL_IN, *PSendRPL_IN;
````


## -struct-fields

### -field PortWWN

Contains a worldwide name for the local port through which the read port list (RPL) command is sent. 


### -field AgentWWN

Contains a worldwide name for the port that is to be queried for a list of ports of type FC_Port. For a definition of FC_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i>. 


### -field agent_domain

Contains the domain number for the domain controller that is to be queried for a list of ports of type FC_Port. For a definition of FC_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i>. 


### -field portIndex

Contains the port index of the first port in the list of ports of type FC_Port to be returned. 


## -remarks
The WMI tool suite generates a declaration of the SendRPL_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="storage.msfc_hbaadaptermethods_wmi_class">MSFC_HBAAdapterMethods WMI Class</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.sendrpl">SendRPL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendRPL_IN structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

