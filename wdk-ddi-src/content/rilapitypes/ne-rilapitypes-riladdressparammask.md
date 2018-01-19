---
UID : NE:rilapitypes.RILADDRESSPARAMMASK
title : RILADDRESSPARAMMASK
author : windows-driver-content
description : This enumeration describes the RILADDRESSPARAMMASK enumeration.
old-location : netvista\riladdressparammask.htm
old-project : netvista
ms.assetid : 02d77f8f-9327-40e4-b38b-7f1a02abf4b1
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILADDRESSPARAMMASK, RILADDRESSPARAMMASK
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : rilapitypes.h
req.include-header : Rilapitypes.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RILADDRESSPARAMMASK
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
req.typenames : RILADDRESSPARAMMASK
req.product : Windows 10 or later.
---

# RILADDRESSPARAMMASK Enumeration


## Syntax
````
enum RILADDRESSPARAMMASK {
  RIL_PARAM_A_NONE     = 0x00000000, 
  RIL_PARAM_A_TYPE     = 0x00000001, 
  RIL_PARAM_A_NUMPLAN  = 0x00000002, 
  RIL_PARAM_A_ADDRESS  = 0x00000004, 
  RIL_PARAM_A_ALL      = 0x00000007 

};
````

## Constants

<table>

<tr>
<td>RIL_PARAM_A_ADDRESS</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_A_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_A_NONE</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_A_NUMPLAN</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_A_TYPE</td>
<td></td>
</tr>
</table>


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
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILADDRESSPARAMMASK enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>