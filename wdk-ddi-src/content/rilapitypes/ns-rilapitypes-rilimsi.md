---
UID : NS:rilapitypes.RILIMSI
title : RILIMSI
author : windows-driver-content
description : This structure represents a RILIMSI.
old-location : netvista\rilimsi.htm
old-project : netvista
ms.assetid : e2dc6a60-b3a6-4b2a-8a6c-aa513ca9b87b
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILIMSI, *LPRILIMSI, rilapitypes/RILIMSI, netvista.rilimsi, RILIMSI structure [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : rilapitypes.h
req.include-header : Rilapitypes.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*LPRILIMSI, RILIMSI"
req.product : Windows 10 or later.
---

# RILIMSI structure
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILIMSI.

<code>const int MAXLENGTH_IMSI = 16</code>

## Syntax
````
struct RILIMSI {
  DWORD cbSize;
  DWORD dwParams;
  WCHAR wszImsi[MAXLENGTH_IMSI];
  DWORD dwMcc;
  DWORD dwMnc;
};
````

## Members


`cbSize`

The size of the structure in bytes.

`dwMcc`

The mobile country code from the IMSI.

`dwMnc`

The mobile network code from the IMSI.

`dwParams`

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilimsiparammask.md">RILIMSIPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

`wszImsi`

The IMSI as a null-terminated Unicode string.

## Remarks
The RIL driver is responsible for determining whether the MNC comprises two or three digits and extracting it accordingly. (For 3GPP, the number of digits in the MNC is specified by the fourth byte of EFAD as specified in 3GPP TS 31.102 section 4.2.18.)

For 3GPP2, the IMSI_T is returned if it is programmed; otherwise, the IMSI_M is returned. For the IMSI_T, dwMcc contains the MCC_Tp and dwMnc contains IMSI_T_11_12p. For the IMSI_M, dwMcc contains the MCC_Mp and dwMnc is not defined (that is, the RIL_PARAM_IMSI_MNC bit in dwParams is 0).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILIMSI structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>