---
UID: NS.WWAN._WWAN_AUTH_SIM_CHALLENGE
title: _WWAN_AUTH_SIM_CHALLENGE
author: windows-driver-content
description: The WWAN_AUTH_SIM_CHALLENGE structure represents an authentication challenge using the SIM method.
old-location: netvista\wwan_auth_sim_challenge.htm
old-project: netvista
ms.assetid: E07F3ED0-2F20-40D9-AAAE-49C81168B998
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WWAN_AUTH_SIM_CHALLENGE, *PWWAN_AUTH_SIM_CHALLENGE, WWAN_AUTH_SIM_CHALLENGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_AUTH_SIM_CHALLENGE
req.alt-loc: wwan.h
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

# _WWAN_AUTH_SIM_CHALLENGE structure



## -description
The WWAN_AUTH_SIM_CHALLENGE structure represents an authentication challenge using the SIM method.



## -syntax

````
typedef struct _WWAN_AUTH_SIM_CHALLENGE {
  BYTE  Rand1[WWAN_AUTH_RAND_LEN];
  BYTE  Rand2[WWAN_AUTH_RAND_LEN];
  BYTE  Rand3[WWAN_AUTH_RAND_LEN];
  ULONG n;
} WWAN_AUTH_SIM_CHALLENGE, *PWWAN_AUTH_SIM_CHALLENGE;
````


## -struct-fields

### -field Rand1[WWAN_AUTH_RAND_LEN]

The first 128-bit random number challenge value. This member represents a multi-byte value in little-endian format.


### -field Rand2[WWAN_AUTH_RAND_LEN]

The second 128-bit random number challenge value. This member represents a multi-byte value in little-endian format.


### -field Rand3[WWAN_AUTH_RAND_LEN]

The third 128-bit random number challenge value. This member represents a multi-byte value in little-endian format.


### -field n

The number of random number challenges.


## -remarks
The <b>n</b> member can be either <b>2</b> or <b>3</b>, according to RFC 4186. If it is set to <b>2</b>, use the <b>Rand1</b> and <b>Rand2</b> members. If it is set to <b>3</b>, then the <b>Rand1</b>, <b>Rand2</b>, and <b>Rand3</b> members.

The <a href="netvista.wwan_auth_challenge">WWAN_AUTH_CHALLENGE</a> structure uses this structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with  Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.wwan_auth_challenge">WWAN_AUTH_CHALLENGE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_AUTH_SIM_CHALLENGE structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

