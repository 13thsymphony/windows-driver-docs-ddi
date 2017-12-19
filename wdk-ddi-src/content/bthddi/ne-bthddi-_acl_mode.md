---
UID: NE.bthddi._ACL_MODE
title: _ACL_MODE
author: windows-driver-content
description: The ACL_MODE enumeration type is used to list the possible states of an ACL connection.
old-location: bltooth\acl_mode.htm
old-project: bltooth
ms.assetid: 90013f42-9393-4037-8d0d-13fe5d7caa0b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _ACL_MODE, ACL_MODE
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
req.alt-api: ACL_MODE
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
---

# _ACL_MODE enumeration



## -description
The ACL_MODE enumeration type is used to list the possible states of an ACL connection.



## -syntax

````
typedef enum _ACL_MODE { 
  ACL_MODE_ACTIVE        = 0x0,
  ACL_MODE_HOLD          = 0x1,
  ACL_MODE_SNIFF         = 0x2,
  ACL_MODE_PARK          = 0x3,
  ACL_MODE_ENTER_ACTIVE  = 0x4,
  ACL_MODE_ENTER_HOLD    = 0x5,
  ACL_MODE_ENTER_SNIFF   = 0x6,
  ACL_MODE_ENTER_PARK    = 0x7,
  ACL_DISCONNECTED       = 0x8
} ACL_MODE;
````


## -enum-fields

### -field ACL_MODE_ACTIVE

This value indicates the ACL is in an active state.


### -field ACL_MODE_HOLD

This value indicates the ACL is in a hold state.


### -field ACL_MODE_SNIFF

This value indicates the ACL is in a sniffed state.


### -field ACL_MODE_PARK

This value indicates the ACL is in a parked state.


### -field ACL_MODE_ENTER_ACTIVE

This value indicates the ACL is entering an active state.


### -field ACL_MODE_ENTER_HOLD

This value indicates the ACL is entering a hold state.


### -field ACL_MODE_ENTER_SNIFF

This value indicates the ACL is entering a sniffed state.


### -field ACL_MODE_ENTER_PARK

This value indicates the ACL is entering a parked state.


### -field ACL_DISCONNECTED

This value indicates the ACL is disconnected.


## -remarks
The 
    <a href="..\bthddi\ns-bthddi-_brb_acl_get_mode.md">_BRB_ACL_GET_MODE</a> structure uses this
    enumeration.


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
<a href="..\bthddi\ns-bthddi-_brb_acl_get_mode.md">_BRB_ACL_GET_MODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20ACL_MODE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

