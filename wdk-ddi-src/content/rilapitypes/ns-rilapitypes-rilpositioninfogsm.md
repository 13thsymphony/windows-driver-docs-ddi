---
UID: NS:rilapitypes.RILPOSITIONINFOGSM
title: RILPOSITIONINFOGSM
author: windows-driver-content
description: This structure represents RILPOSITIONINFOGSM.
old-location: netvista\rilpositioninfogsm.htm
old-project: netvista
ms.assetid: 86b0510b-54ed-463e-b5d4-a34b0a98c00e
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILPOSITIONINFOGSM, RILPOSITIONINFOGSM, *LPRILPOSITIONINFOGSM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILPOSITIONINFOGSM
req.alt-loc: rilapitypes.h
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
req.typenames: RILPOSITIONINFOGSM, *LPRILPOSITIONINFOGSM
req.product: Windows 10 or later.
---

# RILPOSITIONINFOGSM structure



## -description

## -syntax

````
struct RILPOSITIONINFOGSM {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD dwMobileNetworkCode;
  DWORD dwLocationAreaCode;
  DWORD dwCellID;
  DWORD dwTimingAdvance;
  DWORD dwARFCN;
  DWORD dwBaseStationID;
  DWORD dwRxLevel;
};
````


## -struct-fields

### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilpositioninfogsmparammask.md">RILPOSITIONINFOGSMPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwMobileCountryCode

Mobile country code (0...999)


### -field dwMobileNetworkCode

Mobile Network Code (0...999)


### -field dwLocationAreaCode

Location Area Code (0…65535)


### -field dwCellID

Cell ID (0...65535)


### -field dwTimingAdvance

Timing Advance (0...255) in bit periods, where a bit period is 48/13µs


### -field dwARFCN

Absolute radio frequency channel number of serving cell (0...1023)


### -field dwBaseStationID

Radio base station ID of serving cell (0..63)


### -field dwRxLevel

Received signal strength of serving cell (0...63) where:

(x=0, RSS &lt; -110dBm

x=63, RSS &gt; -49dBm

0 &lt;x &lt;63, -110+x &lt; RSS &lt; -109+x)


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h (include Rilapitypes.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILPOSITIONINFOGSM structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

