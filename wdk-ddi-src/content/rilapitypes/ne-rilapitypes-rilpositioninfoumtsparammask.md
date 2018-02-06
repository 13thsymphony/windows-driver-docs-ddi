---
UID: NE:rilapitypes.RILPOSITIONINFOUMTSPARAMMASK
title: RILPOSITIONINFOUMTSPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILPOSITIONINFOUMTSPARAMMASK.
old-location: netvista\rilpositioninfoumtsparammask.htm
old-project: netvista
ms.assetid: fde2eb3f-ea12-45e6-93d1-7bdb0ea8c6b2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_POSITION_UMTS_LAC, RIL_PARAM_POSITION_UMTS_PATHLOSS, rilapitypes/ RIL_PARAM_POSITION_UMTS_UARFCN, rilapitypes/RIL_PARAM_POSITION_UMTS_LAC, rilapitypes/RIL_PARAM_POSITION_UMTS_ALL, RIL_PARAM_POSITION_UMTS_RSCP, RIL_PARAM_POSITION_UMTS_ECNO, rilapitypes/RILPOSITIONINFOUMTSPARAMMASK, rilapitypes/RIL_PARAM_POSITION_UMTS_MCC, RIL_PARAM_POSITION_UMTS_FREQINFO_DL, rilapitypes/RIL_PARAM_POSITION_UMTS_ECNO, RILPOSITIONINFOUMTSPARAMMASK, RIL_PARAM_POSITION_UMTS_UARFCN, rilapitypes/RIL_PARAM_POSITION_UMTS_FREQINFO_DL, rilapitypes/RIL_PARAM_POSITION_UMTS_RSCP, RIL_PARAM_POSITION_UMTS_ALL, RIL_PARAM_POSITION_UMTS_FREQINFO_NT, RIL_PARAM_POSITION_UMTS_MCC, RIL_PARAM_POSITION_UMTS_PRIMARY_SC, RIL_PARAM_POSITION_UMTS_FREQINFO_UL, netvista.rilpositioninfoumtsparammask, rilapitypes/RIL_PARAM_POSITION_UMTS_CELLID, rilapitypes/RIL_PARAM_POSITION_UMTS_FREQINFO_UL, rilapitypes/RIL_PARAM_POSITION_UMTS_MNC, rilapitypes/RIL_PARAM_POSITION_UMTS_PRIMARY_SC, RIL_PARAM_POSITION_UMTS_CELLID, rilapitypes/RIL_PARAM_POSITION_UMTS_PATHLOSS, RILPOSITIONINFOUMTSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_POSITION_UMTS_MNC, rilapitypes/RIL_PARAM_POSITION_UMTS_FREQINFO_NT
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILPOSITIONINFOUMTSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILPOSITIONINFOUMTSPARAMMASK
req.product: Windows 10 or later.
---

# RILPOSITIONINFOUMTSPARAMMASK Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILPOSITIONINFOUMTSPARAMMASK.

## Syntax
````
enum RILPOSITIONINFOUMTSPARAMMASK {
  RIL_PARAM_POSITION_UMTS_MCC          = 0x00000001, 
  RIL_PARAM_POSITION_UMTS_MNC          = 0x00000002, 
  RIL_PARAM_POSITION_UMTS_LAC          = 0x00000004, 
  RIL_PARAM_POSITION_UMTS_CELLID       = 0x00000008, 
  RIL_PARAM_POSITION_UMTS_FREQINFO_UL  = 0x00000010, 
  RIL_PARAM_POSITION_UMTS_FREQINFO_DL  = 0x00000020, 
  RIL_PARAM_POSITION_UMTS_FREQINFO_NT  = 0x00000040, 
   RIL_PARAM_POSITION_UMTS_UARFCN      = 0x00000080, 
  RIL_PARAM_POSITION_UMTS_PRIMARY_SC   = 0x00000100, 
  RIL_PARAM_POSITION_UMTS_RSCP         = 0x00000200, 
  RIL_PARAM_POSITION_UMTS_ECNO         = 0x00000400, 
  RIL_PARAM_POSITION_UMTS_PATHLOSS     = 0x00000800, 
  RIL_PARAM_POSITION_UMTS_ALL          = 0x00000fff 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_CELLID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_ECNO</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_FREQINFO_DL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_FREQINFO_NT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_FREQINFO_UL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_LAC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_MCC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_MNC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_PATHLOSS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_PRIMARY_SC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_RSCP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_UMTS_UARFCN</td>
                    <td></td>
                </tr>
</table>

    ## Remarks

        Networks will vary, but the following table summarizes which items are returned for common UMTS networks. 

<b>Serving network</b>
<table>
<tr>
<th>Entry</th>
<th>Typically returned?</th>
<th>Range</th>
<th>Comment</th>
</tr>
<tr>
<td>
MobileCountryCode

</td>
<td>
Yes

</td>
<td>
0 through 999

</td>
<td>


</td>
</tr>
<tr>
<td>
MobileNetworkCode

</td>
<td>
Yes

</td>
<td>
0 through 999

</td>
<td>


</td>
</tr>
<tr>
<td>
LocationAreaCode

</td>
<td>
Yes

</td>
<td>
0 through 65,535

</td>
<td>


</td>
</tr>
<tr>
<td>
CellID

</td>
<td>
Yes

</td>
<td>
0 through 268,435,455

</td>
<td>
28 bits; may not always be available

</td>
</tr>
<tr>
<td>
FrequencyInfoUL

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
<tr>
<td>
FrequencyInfoDL

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
<tr>
<td>
FrequencyInfoNT

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
<tr>
<td>
UARFCN

</td>
<td>
Yes

</td>
<td>
0 through 16,383

</td>
<td>
UTRA absolute channel number

</td>
</tr>
<tr>
<td>
PrimaryScramblingCode

</td>
<td>
Yes

</td>
<td>
0 through 511

</td>
<td>


</td>
</tr>
<tr>
<td>
RSCP

</td>
<td>
Yes

</td>
<td>
−25 through −120

</td>
<td>
 Measured in dBm; defined in 25.304

</td>
</tr>
<tr>
<td>
ECNO

</td>
<td>
Yes

</td>
<td>
0 through −50

</td>
<td>
 Measured in dB   

</td>
</tr>
<tr>
<td>
PathLoss

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
</table> 

<b>UMTS neighbors</b> (subject to availability from network)
<table>
<tr>
<th>Entry</th>
<th>Typically returned?</th>
<th>Range</th>
<th>Comment</th>
</tr>
<tr>
<td>
MobileCountryCode

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
<tr>
<td>
MobileNetworkCode

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
<tr>
<td>
LocationAreaCode

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
<tr>
<td>
CellID

</td>
<td>
No

</td>
<td>


</td>
<td>
May not always be available; CellID may not be valid in DCH state

</td>
</tr>
<tr>
<td>
UARFCN

</td>
<td>
Yes

</td>
<td>
0 through 16,383

</td>
<td>
WCDMA layer frequency

</td>
</tr>
<tr>
<td>
PrimaryScramblingCode

</td>
<td>
Yes

</td>
<td>
0 through 511

</td>
<td>


</td>
</tr>
<tr>
<td>
RSCP

</td>
<td>
Yes

</td>
<td>
–25 through −120

</td>
<td>
 Measured in dBm; defined in 25.304

</td>
</tr>
<tr>
<td>
ECNO

</td>
<td>
Yes

</td>
<td>
0 through −50

</td>
<td>
 Measured in dB   

</td>
</tr>
<tr>
<td>
PathLoss

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
</table>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

    ## See Also

        <a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILPOSITIONINFOUMTSPARAMMASK enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>