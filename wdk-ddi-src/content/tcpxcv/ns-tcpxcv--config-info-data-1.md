---
UID: NS.tcpxcv._CONFIG_INFO_DATA_1
title: CONFIG_INFO_DATA_1
author: windows-driver-content
description: The XcvData function uses a CONFIG_INFO_DATA_1 structure when it obtains configuration data for a particular port.
old-location: print\config_info_data_1.htm
old-project: print
ms.assetid: abf484e4-6a11-4727-b195-5eaf6683113e
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: CONFIG_INFO_DATA_1, CONFIG_INFO_DATA_1, *PCONFIG_INFO_DATA_1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: tcpxcv.h
req.include-header: Tcpxcv.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CONFIG_INFO_DATA_1
req.alt-loc: tcpxcv.h
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

# CONFIG_INFO_DATA_1 structure



## -description
<p>The <a href="print.xcvdata">XcvData</a> function uses a CONFIG_INFO_DATA_1 structure when it obtains configuration data for a particular port.</p>


## -syntax

````
typedef struct _CONFIG_INFO_DATA_1 {
  BYTE  Reserved[128];
  DWORD dwVersion;
} CONFIG_INFO_DATA_1, *PCONFIG_INFO_DATA_1;
````


## -struct-fields
<dl>

### -field <b>Reserved</b>

<dd>
<p>Is reserved for system use. This member should be set to a zero-length string.</p>
</dd>

### -field <b>dwVersion</b>

<dd>
<p>Specifies the version of the PORT_DATA_1 structure (currently equal to 1) that will contain the configuration information.</p>
</dd>
</dl>

## -remarks
<p>When the <a href="print.xcvdata">XcvData</a> function is called to obtain port configuration information, its <i>pInputData</i> parameter must be set with the address of a CONFIG_INFO_DATA_1 structure, and its <i>pOutputData</i> parameter must be set with the address of a <a href="..\tcpxcv\ns-tcpxcv--port-data-1.md">PORT_DATA_1</a> structure, which will be filled in when the function returns. Set this function's <i>pszDataName</i> parameter to the string L"GetConfigInfo". </p>

<p>See <a href="NULL">TCPMON Xcv Interface</a> for more information.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Tcpxcv.h (include Tcpxcv.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.xcvdata">XcvData</a>
</dt>
<dt>
<a href="..\tcpxcv\ns-tcpxcv--port-data-1.md">PORT_DATA_1</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20CONFIG_INFO_DATA_1 structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
