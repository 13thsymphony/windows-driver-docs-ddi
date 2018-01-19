---
UID : NS:rilapitypes.RILUMTSMRL
title : RILUMTSMRL
author : windows-driver-content
description : This structure represents a RILUMTSMRL.
old-location : netvista\rilumtsmrl.htm
old-project : netvista
ms.assetid : 72567e37-f37f-43f6-8a3a-3d184cb8de13
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILUMTSMRL, RILUMTSMRL, *LPRILUMTSMRL
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
req.alt-api : RILUMTSMRL
req.alt-loc : rilapitypes.h
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
req.typenames : RILUMTSMRL, *LPRILUMTSMRL
req.product : Windows 10 or later.
---

# RILUMTSMRL structure


## Syntax
````
struct RILUMTSMRL {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD dwLocationAreaCode;
  DWORD dwCellID;
  DWORD dwUARFCN;
  DWORD dwPrimaryScramblingCode;
  LONG  dwRSCP;
  LONG  dwECNO;
  DWORD dwPathLoss;
};
````

## Members

        
            `dwCellID`

            UMTS cell ID (0...268435455)
        
            `dwECNO`

            Signal to noise ratio of serving cell; the ratio of the received energy per PN chip for the CPICH to the total received power spectral density at the antenna. Range (-500...0) in units of 0.1dBm.
        
            `dwLocationAreaCode`

            Location area code (0...65535)
        
            `dwMobileCountryCode`

            Country code (0...999)
        
            `dwParams`

            A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilumtsmrlparammask.md">RILUMTSMRLPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.
        
            `dwPathLoss`

            Path loss.
        
            `dwPrimaryScramblingCode`

            Primary Scrambling Code (0...511)
        
            `dwRSCP`

            Received signal code power of serving cell. Range (-1200 ... -250) in units of 0.1dBm, i.e., -250 represents -25dBm.
        
            `dwUARFCN`

            UTRA absolute radio frequency channel number (0...16383)


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUMTSMRL structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>