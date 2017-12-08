---
UID: NE.bthddi._SCO_LINK_TYPE
title: SCO_LINK_TYPE
author: windows-driver-content
description: The SCO_LINK_TYPE enumeration type describes the type of link used by the SCO connection when a ScoIndicationRemoteConnect indication event is processed.
old-location: bltooth\sco_link_type.htm
old-project: bltooth
ms.assetid: 6867a88d-6bce-46eb-894a-cc034a1c3ece
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: IBidiSpl2, UnbindDevice, IBidiSpl2::UnbindDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCO_LINK_TYPE
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
req.iface: IBidiSpl2
---

# SCO_LINK_TYPE enumeration



## -description
<p>The SCO_LINK_TYPE enumeration type describes the type of link used by the SCO connection when a 
  <b>ScoIndicationRemoteConnect</b> indication event is processed.</p>


## -syntax

````
typedef enum _SCO_LINK_TYPE { 
  ScoLinkType   = 0x00,
  eScoLinkType  = 0x02
} SCO_LINK_TYPE, *PSCO_LINK_TYPE;
````


## -enum-fields
<dl>

### -field ScoLinkType

<dd>
<p>This value indicates that the link used by the connection is a SCO link.</p>
</dd>

### -field eScoLinkType

<dd>
<p>This value indicates that the link used by the connection is an eSCO link.</p>
</dd>
</dl>

## -remarks
<p>The 
    <a href="..\bthddi\ns-bthddi--sco-indication-parameters.md">SCO_INDICATION_PARAMETERS</a> structure
    uses this enumeration.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Versions: Supported in Windows Vista, and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\bthddi\ns-bthddi--sco-indication-parameters.md">SCO_INDICATION_PARAMETERS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SCO_LINK_TYPE enumeration%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
