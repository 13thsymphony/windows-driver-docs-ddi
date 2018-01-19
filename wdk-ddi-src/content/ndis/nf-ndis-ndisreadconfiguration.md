---
UID : NF:ndis.NdisReadConfiguration
title : NdisReadConfiguration function
author : windows-driver-content
description : The NdisReadConfiguration function returns the value of a named entry of the specified type from the registry, given the handle to an open registry key.
old-location : netvista\ndisreadconfiguration.htm
old-project : netvista
ms.assetid : 74560229-9e97-40b9-961c-6bf726586e27
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : NdisReadConfiguration
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadConfiguration (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadConfiguration (NDIS   5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NdisReadConfiguration
req.alt-loc : ndis.lib,ndis.dll
req.ddi-compliance : Irql_Miscellaneous_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisReadConfiguration function
The 
  <b>NdisReadConfiguration</b> function returns
  the value of a named entry of the specified type from the registry, given the handle to an open registry
  key. This function must be invoked serially with respect to itself and the <a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a> function.

## Syntax

````
VOID NdisReadConfiguration(
  _Out_ PNDIS_STATUS                  Status,
  _Out_ PNDIS_CONFIGURATION_PARAMETER *ParameterValue,
  _In_  NDIS_HANDLE                   ConfigurationHandle,
  _In_  PNDIS_STRING                  Keyword,
  _In_  NDIS_PARAMETER_TYPE           ParameterType
);
````

## Parameters

`Status`

A pointer to a caller-supplied variable in which this function returns the status of the call as
     one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

`ParameterValue`

A pointer to a memory location where NDIS supplies a pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">
     NDIS_CONFIGURATION_PARAMETER</a> structure if the call to 
     <b>NdisReadConfiguration</b> is
     successful. NDIS allocates memory for the 
     <b>
     NDIS_CONFIGURATION_PARAMETER</b> structure.

`ConfigurationHandle`

The handle to a registry key that was returned by the 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>, 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyindex.md">
     NdisOpenConfigurationKeyByIndex</a>, or 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyname.md">
     NdisOpenConfigurationKeyByName</a> function.

`Keyword`

A pointer to a caller-supplied NDIS_STRING type describing a counted string, in the system-default
     character set, specifying the name of the entry under the open registry key for which to return the
     value. 
     

Alternatively, pointer to a caller-supplied NDIS_STRING_CONSTANT specifying one of the following
     predefined entry names along with predefined return values:

<table>
<tr>
<th>Predefined Entry Name</th>
<th>Predefined Return Values</th>
</tr>
<tr>
<td>
ProcessorType

</td>
<td>

<ul>
<li>NdisProcessorX86</li>
<li>NdisProcessorAmd64</li>
<li>NdisProcessorIA64</li>
<li>NdisProcessorAlpha</li>
</ul> The following are possible only if an old (pre-NDIS 6.0) driver: 
        <ul>
<li>NdisProcessorMips</li>
<li>NdisProcessorPpc</li>
</ul>


</td>
</tr>
<tr>
<td>
NdisVersion

</td>
<td>
0xMMMMmmmm, where 
        <i>MMMM</i> is the major version and 
        <i>mmmm</i> is the minor version number. For example, 0x00050000 indicates that the highest NDIS
        version supported by the system is major version 5, minor version 0.

</td>
</tr>
</table>

`ParameterType`

The type of the value entry that is specified as one of the 
     <a href="..\ndis\ne-ndis-_ndis_parameter_type.md">NDIS_PARAMETER_TYPE</a> enumeration values.
     This parameter is ignored in Windows NT and later versions.


## Return Value

None

## Remarks

In the configuration registry of Windows 2000 and later versions, an NDIS 
    <i>keyword</i> is a synonym for a 
    <i>value entry name</i>. Such a name is a counted sequence of Unicode characters, terminated with a
    <b>NULL</b>.

Every NDIS driver can set up configuration information in the registry for itself using the 
    <b>AddReg</b> directive in its INF file. For example, a protocol driver might store its
    own name as an entry with a preformatted string value that can be passed in calls to the 
    <a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">
    NdisRegisterProtocolDriver</a> function. For more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/add-registry-sections-in-a-network-inf-file">Add-registry-sections in
    a Network INF File</a>.

Each miniport driver also has associated value entries in the registry. The value entries for any
    particular miniport driver can be device-dependent in nature. For example, a miniport driver might have
    keywords such as *FlowControl, *SpeedDuplex, and *InterruptModeration. The value associated with such an
    NDIS keyword can be either an integer (ULONG-type) or a string (NDIS_STRING-type). For example, the set
    of possible values for the already mentioned *FlowControl entry might be <b>NdisParameterInteger</b> values 0,
    1, 2, or 3, or the equivalents in hexadecimal as <b>NdisParameterHexInteger</b> values.

NdisReadConfiguration buffers and copies the caller-supplied string at 
    <i>Keyword</i> and releases the storage it allocates for this copy before it returns control to the
    caller. The memory it allocates for the 
    <a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">
    NDIS_CONFIGURATION_PARAMETER</a> structure is freed when the driver releases the ConfigurationHandle
    with the 
    <a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a> function.
    The caller of 
    <b>NdisReadConfiguration</b> is responsible
    for releasing the buffered string at 
    <i>Keyword</i>.

Note that NDIS does not validate values that a driver reads from the registry. The caller of 
    <b>NdisReadConfiguration</b> must therefore
    not make any assumptions about such values and must validate each value read from the registry. If the
    caller determines that a value is out of bounds, it should use a default value instead.

For more information about setup and installation files, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/overview-of-device-and-driver-installation">Device Installation
    Overview</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">NDIS_CONFIGURATION_PARAMETER</a>
</dt>
<dt>
<a href="..\ndis\ne-ndis-_ndis_parameter_type.md">NDIS_PARAMETER_TYPE</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisansistringtounicodestring.md">
   NdisAnsiStringToUnicodeString</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfreestring.md">NdisFreeString</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisinitansistring.md">NdisInitAnsiString</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisinitializestring.md">NdisInitializeString</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisinitunicodestring.md">NdisInitUnicodeString</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyindex.md">
   NdisOpenConfigurationKeyByIndex</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyname.md">
   NdisOpenConfigurationKeyByName</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreadnetworkaddress.md">NdisReadNetworkAddress</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisunicodestringtoansistring.md">
   NdisUnicodeStringToAnsiString</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReadConfiguration function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>