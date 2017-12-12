---
UID: NF.iddcx.IDD_CX_CLIENT_CONFIG_INIT
title: IDD_CX_CLIENT_CONFIG_INIT function
author: windows-driver-content
description: Initializes the IDD_CX_CLIENT_CONFIG structure.
old-location: display\idd_cx_client_config_init.htm
old-project: display
ms.assetid: 0b2cf0d6-1d69-4917-9e97-f8f2563e6d3c
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: IDD_CX_CLIENT_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDD_CX_CLIENT_CONFIG_INIT
req.alt-loc: iddcx.h
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

# IDD_CX_CLIENT_CONFIG_INIT function



## -description

                        Initializes the IDD_CX_CLIENT_CONFIG structure.
                



## -syntax

````
VOID IDD_CX_CLIENT_CONFIG_INIT(
  _Out_ IDD_CX_CLIENT_CONFIG *Config
);
````


## -parameters

### -param Config [out]

A pointer to the driver-allocated IDD_CX_CLIENT_CONFIG structure.


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
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>