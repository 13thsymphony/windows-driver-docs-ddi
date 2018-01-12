---
UID: NE:rilapitypes.RILTDSCDMAMRLPARAMMASK
title: RILTDSCDMAMRLPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILTDSCDMAMRLPARAMMASK.
old-location: netvista\riltdscdmamrlparammask.htm
old-project: netvista
ms.assetid: d2cc4c39-b96e-4078-bfea-2e06a07e938e
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILTDSCDMAMRLPARAMMASK, RILTDSCDMAMRLPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILTDSCDMAMRLPARAMMASK
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
req.typenames: RILTDSCDMAMRLPARAMMASK
req.product: Windows 10 or later.
---

# RILTDSCDMAMRLPARAMMASK enumeration



## -description

## -syntax

````
enum RILTDSCDMAMRLPARAMMASK {
  RIL_PARAM_TDSCDMAMRL_MCC        = 0x00000001, 
  RIL_PARAM_TDSCDMAMRL_MNC        = 0x00000002, 
  RIL_PARAM_TDSCDMAMRL_LAC        = 0x00000004, 
  RIL_PARAM_TDSCDMAMRL_CELLID     = 0x00000008, 
  RIL_PARAM_TDSCDMAMRL_UARFCN     = 0x00000010, 
  RIL_PARAM_TDSCDMAMRL_CELLPARAM  = 0x00000020, 
  RIL_PARAM_TDSCDMAMRL_RSCP       = 0x00000040, 
  RIL_PARAM_TDSCDMAMRL_PATHLOSS   = 0x00000080, 
  RIL_PARAM_TDSCDMAMRL_ALL        = 0x000000ff 

};
````


## -enum-fields

### -field RIL_PARAM_TDSCDMAMRL_MCC


### -field RIL_PARAM_TDSCDMAMRL_MNC


### -field RIL_PARAM_TDSCDMAMRL_LAC


### -field RIL_PARAM_TDSCDMAMRL_CELLID


### -field RIL_PARAM_TDSCDMAMRL_UARFCN


### -field RIL_PARAM_TDSCDMAMRL_CELLPARAM


### -field RIL_PARAM_TDSCDMAMRL_RSCP


### -field RIL_PARAM_TDSCDMAMRL_PATHLOSS


### -field RIL_PARAM_TDSCDMAMRL_ALL


## -remarks
Networks will vary, but the following table summarizes which items are returned for typical TD-SCDMA networks. 

<b>Serving network</b>

MobileCountryCode

Yes

0 through 999



MobileNetworkCode

LocationAreaCode

0 to 65535

CellID

0 through 268,435,455

May not always be available; 28 bits

UARFCN

0 through 16,383

Channel number

CellParameterID

0 through 127

TimingAdvance

0 through 8,191

By standards, the maximum range is 96 chips (0 to 96x8)

RSCP

−25 through −128

Received signal code power of serving cell in dBm  

PathLoss

No

46 through 158

Path loss of serving cell in dBs  

<b>TD-SCDMA neighbors</b> (subject to availability from network)


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
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILTDSCDMAMRLPARAMMASK enumeration%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

