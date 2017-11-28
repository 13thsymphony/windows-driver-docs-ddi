---
UID: NS.ndis._NDIS_CONFIGURATION_PARAMETER
title: NDIS_CONFIGURATION_PARAMETER
author: windows-driver-content
description: The NDIS_CONFIGURATION_PARAMETER structure contains the data and type of a named entry in the registry.
old-location: netvista\ndis_configuration_parameter.htm
old-project: netvista
ms.assetid: 80250799-4263-43c0-85d5-f1c1c1fb0bae
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NDIS_CONFIGURATION_PARAMETER, NDIS_CONFIGURATION_PARAMETER, *PNDIS_CONFIGURATION_PARAMETER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS
   5.1 drivers in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_CONFIGURATION_PARAMETER
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
req.irql: See Remarks section
req.iface: 
---

# NDIS_CONFIGURATION_PARAMETER structure



## -description
<p>The NDIS_CONFIGURATION_PARAMETER structure contains the data and type of a named entry in the
  registry.</p>


## -syntax

````
typedef struct _NDIS_CONFIGURATION_PARAMETER {
  NDIS_PARAMETER_TYPE ParameterType;
  union {
    ULONG       IntegerData;
    NDIS_STRING StringData;
    BINARY_DATA BinaryData;
  } ParameterData;
} NDIS_CONFIGURATION_PARAMETER, *PNDIS_CONFIGURATION_PARAMETER;
````


## -struct-fields
<dl>

### -field <b>ParameterType</b>

<dd>
<p>The type of the parameter specified as one of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566740">NDIS_PARAMETER_TYPE</a> enumeration values. 
     </p>
<p>For successful calls to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a> function, the
     
     <b>ParameterType</b> value matches the value at the 
     <i>ParameterType</i> parameter. However, when the 
     <i>ParameterType</i> parameter is 
     <b>NdisParameterHexInteger</b>, the resulting 
     <b>ParameterType</b> member value is 
     <b>NdisParameterInteger</b>.</p>
</dd>

### -field <b>ParameterData</b>

<dd>
<p>A union that contains the value of the given named entry. If ParameterType is a string type, this
      member is an NDIS_STRING type describing a counted string in the system-default character set. For
      Microsoft Windows 2000 and later drivers, such a string contains Unicode characters. That is, for
      Windows 2000 and later, NDIS defines the NDIS_STRING type as a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> type.</p>
<p>This union contains the following members:</p>
<dl>

### -field <b>IntegerData</b>

<dd>
<p>A ULONG value that is used when the 
      <b>ParameterType</b> member is set to 
      <b>NdisParameterInteger</b> or 
      <b>NdisParameterHexInteger</b>.</p>
</dd>

### -field <b>StringData</b>

<dd>
<p>An NDIS_STRING value that is used when the 
      <b>ParameterType</b> member is set to 
      <b>NdisParameterString</b> or 
      <b>NdisParameterMultiString</b>.</p>
</dd>

### -field <b>BinaryData</b>

<dd>
<p>A 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff543838">BINARY_DATA</a> structure that is used when the 
      <b>ParameterType</b> member is set to 
      <b>NdisParameterBinary</b>.</p>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>To read parameters in the registry, an NDIS driver can call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a> function. If
    the call is successful, NDIS returns a pointer to an NDIS_CONFIGURATION_PARAMETER structure at the 
    <i>ParameterValue</i> parameter of 
    <b>NdisReadConfiguration</b>.</p>

<p>To write parameters to the registry, an NDIS driver can call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564659">NdisWriteConfiguration</a> function. In
    this case, the driver initializes an NDIS_CONFIGURATION_PARAMETER structure and passes it at the 
    <i>ParameterValue</i> parameter of 
    <b>NdisWriteConfiguration</b>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS
   5.1 drivers in Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543838">BINARY_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566740">NDIS_PARAMETER_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564659">NdisWriteConfiguration</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_CONFIGURATION_PARAMETER structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
