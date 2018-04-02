---
UID: NS:ndis._NDIS_CONFIGURATION_PARAMETER
title: "_NDIS_CONFIGURATION_PARAMETER"
author: windows-driver-content
description: The NDIS_CONFIGURATION_PARAMETER structure contains the data and type of a named entry in the registry.
old-location: netvista\ndis_configuration_parameter.htm
old-project: netvista
ms.assetid: 80250799-4263-43c0-85d5-f1c1c1fb0bae
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_CONFIGURATION_PARAMETER, NDIS_CONFIGURATION_PARAMETER, NDIS_CONFIGURATION_PARAMETER structure [Network Drivers Starting with Windows Vista], PNDIS_CONFIGURATION_PARAMETER, PNDIS_CONFIGURATION_PARAMETER structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CONFIGURATION_PARAMETER, ndis/NDIS_CONFIGURATION_PARAMETER, ndis/PNDIS_CONFIGURATION_PARAMETER, ndis_configuration_ref_14664bdb-06c7-4d27-b71b-d6a69f3e3396.xml, netvista.ndis_configuration_parameter"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_CONFIGURATION_PARAMETER
product:
- Windows
targetos: Windows
req.typenames: NDIS_CONFIGURATION_PARAMETER, *PNDIS_CONFIGURATION_PARAMETER
---

# _NDIS_CONFIGURATION_PARAMETER structure
The NDIS_CONFIGURATION_PARAMETER structure contains the data and type of a named entry in the
  registry.

## Syntax
```
typedef struct _NDIS_CONFIGURATION_PARAMETER {
  NDIS_PARAMETER_TYPE ParameterType;
  union {
    BINARY_DATA BinaryData;
    ULONG       IntegerData;
    NDIS_STRING StringData;
  } ParameterData;
} NDIS_CONFIGURATION_PARAMETER, *PNDIS_CONFIGURATION_PARAMETER;
```

## Members


`ParameterType`

The type of the parameter specified as one of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566740">NDIS_PARAMETER_TYPE</a> enumeration values. 
     

For successful calls to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a> function, the
     
     <b>ParameterType</b> value matches the value at the 
     <i>ParameterType</i> parameter. However, when the 
     <i>ParameterType</i> parameter is 
     <b>NdisParameterHexInteger</b>, the resulting 
     <b>ParameterType</b> member value is 
     <b>NdisParameterInteger</b>.

`ParameterData`

A union that contains the value of the given named entry. If ParameterType is a string type, this
      member is an NDIS_STRING type describing a counted string in the system-default character set. For
      Microsoft Windows 2000 and later drivers, such a string contains Unicode characters. That is, for
      Windows 2000 and later, NDIS defines the NDIS_STRING type as a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> type.

This union contains the following members:



#### IntegerData

A ULONG value that is used when the 
      <b>ParameterType</b> member is set to 
      <b>NdisParameterInteger</b> or 
      <b>NdisParameterHexInteger</b>.



#### StringData

An NDIS_STRING value that is used when the 
      <b>ParameterType</b> member is set to 
      <b>NdisParameterString</b> or 
      <b>NdisParameterMultiString</b>.



#### BinaryData

A 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff543838">BINARY_DATA</a> structure that is used when the 
      <b>ParameterType</b> member is set to 
      <b>NdisParameterBinary</b>.

## Remarks
To read parameters in the registry, an NDIS driver can call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a> function. If
    the call is successful, NDIS returns a pointer to an NDIS_CONFIGURATION_PARAMETER structure at the 
    <i>ParameterValue</i> parameter of 
    <b>NdisReadConfiguration</b>.

To write parameters to the registry, an NDIS driver can call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564659">NdisWriteConfiguration</a> function. In
    this case, the driver initializes an NDIS_CONFIGURATION_PARAMETER structure and passes it at the 
    <i>ParameterValue</i> parameter of 
    <b>NdisWriteConfiguration</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543838">BINARY_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566740">NDIS_PARAMETER_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564659">NdisWriteConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>