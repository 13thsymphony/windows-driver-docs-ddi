---
UID: NS:gnssdriver.GNSS_SUPL_NI_INFO
title: GNSS_SUPL_NI_INFO
author: windows-driver-content
description: This structure contains the requested SUPL NI information.
old-location: sensors\gnss_supl_ni_info.htm
old-project: sensors
ms.assetid: 78D19A0C-E247-4DDA-A689-494B5A61A673
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_SUPL_NI_INFO, GNSS_SUPL_NI_INFO, *PGNSS_SUPL_NI_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_SUPL_NI_INFO
req.alt-loc: gnssdriver.h
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
req.typenames: GNSS_SUPL_NI_INFO, *PGNSS_SUPL_NI_INFO
---

# GNSS_SUPL_NI_INFO structure



## -description
This structure contains the requested SUPL NI information.



## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
  WCHAR RequestorId[MAX_PATH];
  WCHAR ClientName[MAX_PATH];
  CHAR  SuplNiUrl[MAX_SERVER_URL_NAME];
} GNSS_SUPL_NI_INFO, *PGNSS_SUPL_NI_INFO;
````


## -struct-fields

### -field Size

Structure size.


### -field Version

Version number.


### -field RequestorId[MAX_PATH]

Requestor ID.

This will be displayed on the notification dialog to the user. The GNSS driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.


### -field ClientName[MAX_PATH]

Name of the client that requests the location of the device.

This will be displayed on the notification dialog to the user. The GNSS driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.


### -field SuplNiUrl[MAX_SERVER_URL_NAME]

NI URL information.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>