---
UID: NS.NTDDPAR._PARCLASS_NEGOTIATION_MASK
title: _PARCLASS_NEGOTIATION_MASK
author: windows-driver-content
description: The PARCLASS_NEGOTIATION_MASK structure specifies the read and write protocols that a driver selects for a parallel device.
old-location: parports\parclass_negotiation_mask.htm
old-project: parports
ms.assetid: 6d246ec3-47f1-46da-8ac4-f073f91c0d44
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _PARCLASS_NEGOTIATION_MASK, PARCLASS_NEGOTIATION_MASK, *PPARCLASS_NEGOTIATION_MASK, PPARCLASS_NEGOTIATION_MASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddpar.h
req.include-header: Ntddpar.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PARCLASS_NEGOTIATION_MASK
req.alt-loc: ntddpar.h
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

# _PARCLASS_NEGOTIATION_MASK structure



## -description
The PARCLASS_NEGOTIATION_MASK structure specifies the read and write protocols that a driver selects for a parallel device.



## -syntax

````
typedef struct _PARCLASS_NEGOTIATION_MASK {
  USHORT usReadMask;
  USHORT usWriteMask;
} PARCLASS_NEGOTIATION_MASK, *PPARCLASS_NEGOTIATION_MASK;
````


## -struct-fields

### -field usReadMask

Specifies the read protocols. For read and write protocol values, see the constants that are defined in <i>ntddpar.h</i> (from NONE to ECP_ANY).


### -field usWriteMask

Specifies the write protocols.


## -remarks
A client specifies a set of requested protocols by setting a bitwise OR of the constants that represent each protocol. The system-supplied bus driver for parallel ports selects the fastest protocol that it supports from among those specified by the client. 

For more information, see <a href="https://msdn.microsoft.com/2ff53ed0-dbb7-4c8f-b6e4-5f7d20124a7c">Setting and Clearing a Communication Mode for a Parallel Device</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddpar.h (include Ntddpar.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>
</dt>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>
</dt>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pdetermine_ieee_modes.md">PDETERMINE_IEEE_MODES</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PARCLASS_NEGOTIATION_MASK structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

