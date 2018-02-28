---
UID: NS:rilapitypes.RILPOSITIONINFO_V2
title: RILPOSITIONINFO_V2
author: windows-driver-content
description: This structure represents the RILPOSITIONINFO_V2.
old-location: netvista\rilpositioninfo_v2.htm
old-project: netvista
ms.assetid: 881e85a2-4ba2-4940-94c0-61a2d335e52a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILPOSITIONINFO, *LPRILPOSITIONINFO_V2, RILPOSITIONINFO, RILPOSITIONINFO_V2, RILPOSITIONINFO_V2 structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfo_v2, rilapitypes/RILPOSITIONINFO_V2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILPOSITIONINFO_V2
product: Windows
targetos: Windows
req.typenames: RILPOSITIONINFO_V2, *LPRILPOSITIONINFO_V2, RILPOSITIONINFO, *LPRILPOSITIONINFO
req.product: Windows 10 or later.
---

# RILPOSITIONINFO_V2 structure
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents the RILPOSITIONINFO_V2.

## Syntax
````
struct RILPOSITIONINFO_V2 {
  DWORD                  cbSize;
  DWORD                  dwSystemType;
  RILPOSITIONINFOGSM     stGSMServingCellInfo;
  RILPOSITIONINFOUMTS    stUMTSServingCellInfo;
  RILPOSITIONINFOTDSCDMA stTDSCDMAServingCellInfo;
  RILPOSITIONINFOLTE     stLTEServingCellInfo;
  DWORD                  dwCntGSMNMR;
  RILGSMNMR              rgNMR[MAX_GSMPOS_COUNT_OF_NMR];
  DWORD                  dwCntUMTSMRL;
  ruMRL                  RILUMTSMRL[MAX_UMTSPOS_COUNT_OF_MRL];
  DWORD                  dwCntTDSCDMAMRL;
  rtMRL                  RILTDSCDMAMRL[MAX_TDSCDMAPOS_COUNT_OF_MRL];
  DWORD                  dwCntEUTRAMRL;
  RILEUTRAMRL            reMRL[MAX_EUTRAPOS_COUNT_OF_MRL];
  DWORD                  dwCntC2KMRL;
  RILC2KMRL              rc2kMRL[MAX_C2KPOS_COUNT_OF_MRL];
};
````

## Members


`cbSize`

The size of the structure in bytes.

`dwCntC2KMRL`

The number of entries in the cdma2000 measured results list <b>rc2kMRL</b>.

`dwCntEUTRAMRL`

The number of entries in the EUTRAN (LTE) measured results list <b>reMRL</b>.

`dwCntGSMNMR`

The number of GSM network measurement reports in <b>rgNMR</b>.

`dwCntTDSCDMAMRL`

The number of entries in the TD-SCDMA measured results list <b>rtMRL</b>. This field is not present in RILPOSITIONINFO_V1.

`dwCntUMTSMRL`

The number of entries in the UMTS measured results list <b>ruMRL</b>.

`dwSystemType`

Indicates the system type or types for which serving cell information is valid, a bitmask of one or more <a href="..\rilapitypes\ne-rilapitypes-rilsystemtype.md">RILSYSTEMTYPE</a> values. For example, on an SVLTE system, this could be <code>RIL_SYSTEMTYPE_LTE|RIL_SYSTEMTYPE_1XRTT</code>, indicating that both the CDMA cell information (including serving cell(s)) in <b>rc2kMRL</b> and <b>stLTEServingCellInfo</b> are valid.

`rc2kMRL`

The cdma2000 measured results list, an array of <a href="..\rilapitypes\ns-rilapitypes-rilc2kmrl.md">RILC2KMRL</a> structs.

`reMRL`

E-UTRAN (LTE) measured results list, an array of <a href="..\rilapitypes\ns-rilapitypes-rileutramrl.md">RILEUTRAMRL</a> structs.

`rgNMR`

GSM network measurement reports, an array of <a href="..\rilapitypes\ns-rilapitypes-rilgsmnmr.md">RILGSMNMR</a> structs.

`rtMRL`



`ruMRL`



`stGSMServingCellInfo`

GSM serving cell information, a <a href="..\rilapitypes\ns-rilapitypes-rilpositioninfogsm.md">RILPOSITIONINFOGSM</a> struct.

`stLTEServingCellInfo`

LTE serving cell information, a <a href="..\rilapitypes\ns-rilapitypes-rilpositioninfolte.md">RILPOSITIONINFOLTE</a> struct.

`stTDSCDMAServingCellInfo`

TD-SCDMA serving cell information, a <a href="..\rilapitypes\ns-rilapitypes-rilpositioninfotdscdma.md">RILPOSITIONINFOTDSCDMA</a> struct. This field is not present in <a href="https://msdn.microsoft.com/library/windows/hardware/dn931134">RILPOSITIONINFO_V1</a>.

`stUMTSServingCellInfo`

UMTS serving cell information, a <a href="..\rilapitypes\ns-rilapitypes-rilpositioninfoumts.md">RILPOSITIONINFOUMTS</a> struct.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h, Ntddrilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILPOSITIONINFO_V2 structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>