---
UID: NS:bthddi._CO_HEADER
title: _CO_HEADER
author: windows-driver-content
description: The CO_HEADER structure is used to specify values for the Header member of the L2CAP_CONFIG_OPTION structure.
old-location: bltooth\co_header.htm
old-project: bltooth
ms.assetid: 76fa3316-bbec-4bf1-8cb8-d92e9f54d2d6
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _CO_HEADER, CO_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CO_HEADER
req.alt-loc: bthddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
req.typenames: CO_HEADER
---

# _CO_HEADER structure



## -description
The CO_HEADER structure is used to specify values for the 
  <b>Header</b> member of the 
  <a href="..\bthddi\ns-bthddi-_l2cap_config_option.md">L2CAP_CONFIG_OPTION</a> structure.



## -syntax

````
typedef struct _CO_HEADER {
  CO_TYPE   Type;
  CO_LENGTH Length;
} CO_HEADER;
````


## -struct-fields

### -field Type

The type of the vendor-specific option stored in the L2CAP_CONFIG_OPTION structure. This can
     accept either an option or a hint.


### -field Length

The size, in bytes, of the vendor-specific option stored in the L2CAP_CONFIG_OPTION
     structure.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows Vista, and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Bthddi.h (include Bthddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\bthddi\ns-bthddi-_l2cap_config_option.md">L2CAP_CONFIG_OPTION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20CO_HEADER structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

