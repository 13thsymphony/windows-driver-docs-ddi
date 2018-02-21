---
UID: NE:ndis._NDIS_PARAMETER_TYPE
title: "_NDIS_PARAMETER_TYPE"
author: windows-driver-content
description: The NDIS_PARAMETER_TYPE enumeration type identifies the type of a registry entry.
old-location: netvista\ndis_parameter_type.htm
old-project: netvista
ms.assetid: f17e390a-fa13-4435-ad1e-3fecc035ec41
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisParameterHexInteger, ndis/NdisParameterHexInteger, NDIS_PARAMETER_TYPE, NdisParameterBinary, ndis/PNDIS_PARAMETER_TYPE, PNDIS_PARAMETER_TYPE, NdisParameterString, netvista.ndis_parameter_type, ndis/NdisParameterBinary, NdisParameterMultiString, PNDIS_PARAMETER_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], ndis/NDIS_PARAMETER_TYPE, NdisParameterInteger, ndis/NdisParameterInteger, *PNDIS_PARAMETER_TYPE, NDIS_PARAMETER_TYPE enumeration [Network Drivers Starting with Windows Vista], ndis/NdisParameterString, _NDIS_PARAMETER_TYPE, ndis/NdisParameterMultiString, ndis_configuration_ref_05a453df-2660-470b-8eaf-7a59dcb20e04.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NDIS_PARAMETER_TYPE
product: Windows
targetos: Windows
req.typenames: NDIS_PARAMETER_TYPE, *PNDIS_PARAMETER_TYPE
---

# _NDIS_PARAMETER_TYPE Enumeration
The NDIS_PARAMETER_TYPE enumeration type identifies the type of a registry entry.

## Syntax
````
typedef enum _NDIS_PARAMETER_TYPE { 
  NdisParameterInteger,
  NdisParameterHexInteger,
  NdisParameterString,
  NdisParameterMultiString,
  NdisParameterBinary
} NDIS_PARAMETER_TYPE, *PNDIS_PARAMETER_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>NdisParameterBinary</td>
                    <td>A binary value of type REG_BINARY.</td>
                </tr>
            
                <tr>
                    <td>NdisParameterHexInteger</td>
                    <td>An integer in hexadecimal notation.</td>
                </tr>
            
                <tr>
                    <td>NdisParameterInteger</td>
                    <td>An integer in decimal notation.</td>
                </tr>
            
                <tr>
                    <td>NdisParameterMultiString</td>
                    <td>A multistring parameter of the REG_MULTI_SZ type.</td>
                </tr>
            
                <tr>
                    <td>NdisParameterString</td>
                    <td>A string of type NDIS_STRING.</td>
                </tr>
</table>

## Remarks

The NDIS_PARAMETER_TYPE enumeration type is used in the 
    <a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">
    NDIS_CONFIGURATION_PARAMETER</a> structure and in the 
    <i>ParameterType</i> parameter of the 
    <a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>



<a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">NDIS_CONFIGURATION_PARAMETER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PARAMETER_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>