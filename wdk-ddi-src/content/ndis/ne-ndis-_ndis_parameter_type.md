---
UID: NE:ndis._NDIS_PARAMETER_TYPE
title: _NDIS_PARAMETER_TYPE
author: windows-driver-content
description: The NDIS_PARAMETER_TYPE enumeration type identifies the type of a registry entry.
old-location: netvista\ndis_parameter_type.htm
old-project: netvista
ms.assetid: f17e390a-fa13-4435-ad1e-3fecc035ec41
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_PARAMETER_TYPE, *PNDIS_PARAMETER_TYPE, NDIS_PARAMETER_TYPE
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
req.alt-api: NDIS_PARAMETER_TYPE
req.alt-loc: ndis.h
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
req.typenames: *PNDIS_PARAMETER_TYPE, NDIS_PARAMETER_TYPE
---

# _NDIS_PARAMETER_TYPE enumeration



## -description
The NDIS_PARAMETER_TYPE enumeration type identifies the type of a registry entry.



## -syntax

````
typedef enum _NDIS_PARAMETER_TYPE { 
  NdisParameterInteger,
  NdisParameterHexInteger,
  NdisParameterString,
  NdisParameterMultiString,
  NdisParameterBinary
} NDIS_PARAMETER_TYPE, *PNDIS_PARAMETER_TYPE;
````


## -enum-fields

### -field NdisParameterInteger

An integer in decimal notation.


### -field NdisParameterHexInteger

An integer in hexadecimal notation.


### -field NdisParameterString

A string of type NDIS_STRING.


### -field NdisParameterMultiString

A multistring parameter of the REG_MULTI_SZ type.


### -field NdisParameterBinary

A binary value of type REG_BINARY.


## -remarks
The NDIS_PARAMETER_TYPE enumeration type is used in the 
    <a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">
    NDIS_CONFIGURATION_PARAMETER</a> structure and in the 
    <i>ParameterType</i> parameter of the 
    <a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a> function.


## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">NDIS_CONFIGURATION_PARAMETER</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PARAMETER_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

