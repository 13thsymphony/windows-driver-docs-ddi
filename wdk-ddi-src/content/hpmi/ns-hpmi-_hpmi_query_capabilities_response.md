---
UID: NS.HPMI._HPMI_QUERY_CAPABILITIES_RESPONSE
title: _HPMI_QUERY_CAPABILITIES_RESPONSE
author: windows-driver-content
description: HPMI_QUERY_CAPABILITIES_RESPONSE is a structure used to return information about software defined batteries (SDB).
old-location: powermeter\hpmi_query_capabilities_response.htm
old-project: powermeter
ms.assetid: 2D7B6278-6D7A-41C4-B21A-D531CD8DCD91
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _HPMI_QUERY_CAPABILITIES_RESPONSE, *PHPMI_QUERY_CAPABILITIES_RESPONSE, HPMI_QUERY_CAPABILITIES_RESPONSE, PHPMI_QUERY_CAPABILITIES_RESPONSE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hpmi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HPMI_QUERY_CAPABILITIES_RESPONSE
req.alt-loc: hpmi.h
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

# _HPMI_QUERY_CAPABILITIES_RESPONSE structure



## -description
HPMI_QUERY_CAPABILITIES_RESPONSE is a structure used to return information about software defined batteries (SDB).



## -syntax

````
typedef struct _HPMI_QUERY_CAPABILITIES_RESPONSE {
  ULONG  Version;
  ULONG  RequestService;
  ULONG  SdbCapabilities;
} HPMI_QUERY_CAPABILITIES_RESPONSE, *PHPMI_QUERY_CAPABILITIES_RESPONSE;
````


## -struct-fields

### -field Version

Set to HPMI_QUERY_CAPABILITIES_VERSION_1.  


### -field RequestService

Requests one or more Windows services as defined by
    HPMI_REQUEST_SERVICE_XXX.


### -field SdbCapabilities

Specifies Software Defined Battery (SDB) features supported by the system.

 This field is set to combination of one or more HPMI_CAPABILITY_SDB_XXX
    values logically OR'd. It should be set to HPMI_CAPABILITY_NOT_SUPPORTED to
    indicate that SDB is not supported.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 10, version 1709 and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hpmi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="powermeter.hpmi_h">hpmi.h</a>
</dt>
<dt>
<a href="powermeter.hpmi_query_capabilities">HPMI_QUERY_CAPABILITIES</a>
</dt>
<dt>
<a href="..\hpmi\ni-hpmi-ioctl_hpmi_query_capabilities.md">IOCTL_HPMI_QUERY_CAPABILITIES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20HPMI_QUERY_CAPABILITIES_RESPONSE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

