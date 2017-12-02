---
UID: NF.ndis.NdisWriteConfiguration
title: NdisWriteConfiguration
author: windows-driver-content
description: The NdisWriteConfiguration function writes a caller-supplied value for a specified entry into the registry. This function must be invoked serially with respect to itself and the NdisReadConfiguration function.
old-location: netvista\ndiswriteconfiguration.htm
old-project: netvista
ms.assetid: 63c94f4d-1c8c-43c2-ae58-993da42a80a4
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NdisWriteConfiguration
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteConfiguration (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteConfiguration (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisWriteConfiguration
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# NdisWriteConfiguration function



## -description
<p>The 
  <b>NdisWriteConfiguration</b> function writes a caller-supplied value for a specified entry into the
  registry. This function must be invoked serially with respect to itself and the <a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a> function.</p>


## -syntax

````
VOID NdisWriteConfiguration(
  _Out_ PNDIS_STATUS                  Status,
  _In_  NDIS_HANDLE                   ConfigurationHandle,
  _In_  PNDIS_STRING                  Keyword,
  _In_  PNDIS_CONFIGURATION_PARAMETER ParameterValue
);
````


## -parameters
<dl>

### -param Status [out]

<dd>
<p>A pointer to a caller-supplied variable in which this function returns the status of the call as
     one of the following:
     </p>
<p></p>
<dl>

### -param NDIS_STATUS_SUCCESS

<dd>
<p>The supplied value at 
       <i>ParameterValue</i> was written into the registry. If this is a new entry, the name at 
       <i>Keyword</i> also was written into the registry.</p>
</dd>

### -param NDIS_STATUS_NOT_SUPPORTED

<dd>
<p>The supplied 
       <b>ParameterType</b> is invalid.</p>
</dd>

### -param NDIS_STATUS_RESOURCES

<dd>
<p>NDIS could not allocate resources, usually enough memory, to transfer the requested information
       to the registry.</p>
</dd>

### -param NDIS_STATUS_FAILURE

<dd>
<p>The requested information could not be written.</p>
</dd>
</dl>
</dd>

### -param ConfigurationHandle [in]

<dd>
<p>The handle to a registry key that was returned by the 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>, 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyindex.md">
     NdisOpenConfigurationKeyByIndex</a>, or 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyname.md">
     NdisOpenConfigurationKeyByName</a> function.</p>
</dd>

### -param Keyword [in]

<dd>
<p>A pointer to an NDIS_STRING type describing a caller-supplied counted string, in the
     system-default character set, specifying the name of an entry for which to write the value. For
     Microsoft Windows 2000 and later drivers, this string contains Unicode characters. That is, for Windows
     2000 and later, NDIS defines the NDIS_STRING type as a 
     <a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a> type.</p>
</dd>

### -param ParameterValue [in]

<dd>
<p>Pointer to a caller-supplied 
     <a href="..\ndis\ns-ndis--ndis-configuration-parameter.md">
     NDIS_CONFIGURATION_PARAMETER</a> structure.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If an entry of the same name as at 
    <i>Keyword</i> already exists under the opened registry key, 
    <b>NdisWriteConfiguration</b> replaces its current value with the caller-supplied value. Otherwise, 
    <b>NdisWriteConfiguration</b> adds a new value entry with the given name and supplied value to the
    registry.</p>

<p>In the configuration registry of Windows 2000 and later versions, an NDIS 
    <i>Keyword</i> is a synonym for a
    <i>value entry name</i>. Such a name is a counted sequence of Unicode characters, terminated with a
    NUL.</p>

<p><b>NdisWriteConfiguration</b> buffers and copies the caller-supplied string at 
    <i>Keyword</i> and the caller-supplied data specified at 
    <i>ParameterValue</i> . This memory is freed when the driver releases the 
    <i>ConfigurationHandle</i> with the 
    <a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a> function.
    The caller of 
    <b>NdisWriteConfiguration</b> is responsible for releasing the buffered string at 
    <i>Keyword</i> and the memory allocated for the 
    <a href="..\ndis\ns-ndis--ndis-configuration-parameter.md">
    NDIS_CONFIGURATION_PARAMETER</a> structure.</p>

<p>As an alternative to calling 
    <b>NdisWriteConfiguration</b>, every NDIS driver can set up configuration information in the registry for
    itself using the AddReg directive in the driver's INF file.</p>

<p>For more information about setup and installation files for Windows 2000 and later versions, see 
    <a href="devinst.overview_of_device_and_driver_installation">Device Installation
    Overview</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/c6d956fc-b634-4ca6-8597-ceeb1cd8d94f">NdisWriteConfiguration (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisWriteConfiguration (NDIS
   5.1)</b>) in Windows XP.</p>
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
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ansi_string">ANSI_STRING</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-configuration-parameter.md">NDIS_CONFIGURATION_PARAMETER</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisansistringtounicodestring.md">
   NdisAnsiStringToUnicodeString</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a>
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
<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisunicodestringtoansistring.md">
   NdisUnicodeStringToAnsiString</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisWriteConfiguration function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
