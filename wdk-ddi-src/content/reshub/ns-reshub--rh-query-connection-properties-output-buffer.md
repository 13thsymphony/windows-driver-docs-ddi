---
UID: NS.reshub._RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
title: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
author: windows-driver-content
description: The RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER structure contains the connection properties for a target device that is connected to a serial bus (I2C, SPI, or UART).
old-location: spb\rh_query_connection_properties_output_buffer.htm
old-project: SPB
ms.assetid: 36B2C20C-AA92-4860-9FBC-BA65AFD546E1
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: reshub.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.alt-loc: Reshub.h
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
req.iface: 
req.product: Windows 10 or later.
---

# RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER structure



## -description
<p>The <b>RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</b> structure contains the connection properties for a target device that is connected to a serial bus (I2C, SPI, or UART).</p>


## -syntax

````
typedef struct _RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER {
  ULONG Version;
  ULONG PropertiesLength;
  UCHAR ConnectionProperties[ANYSIZE_ARRAY];
} RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER;
````


## -struct-fields
<dl>

### -field Version

<dd>
<p>The version number of this structure. This member is set to the RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_VERSION constant, which is defined in the Reshub.h header file.</p>
</dd>

### -field PropertiesLength

<dd>
<p>The size, in bytes, of the serial bus connection descriptor that starts with element 0 of the <b>ConnectionProperties</b> array.</p>
</dd>

### -field ConnectionProperties

<dd>
<p>The first byte of the serial bus connection descriptor. This byte is immediately followed by the remaining bytes of the descriptor. The <b>PropertiesLength</b> member specifies the total number of bytes occupied by the descriptor. The definition of the <b>ConnectionProperties</b> member uses the ANYSIZE_ARRAY constant, which the Ntdef.h header file defines to be 1. For more information, see Remarks.</p>
</dd>
</dl>

## -remarks
<p>The <b>ConnectionProperties</b> member of the <b>RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</b> structure contains the first byte of the serial bus connection descriptor for the target device. The remaining bytes in the descriptor immediately follow this member in memory. The buffer allocated for the <b>RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</b> structure is large enough to contain this structure plus the remaining bytes of the serial bus connection descriptor that extend past the end of the structure.</p>

<p>The format for the serial bus connection descriptor is described in revision 5.0 of the Advanced Configuration and Power Interface Specification at the <a href="http://www.acpi.info">ACPI</a> website. For convenience, the Reshub.h header file defines the  <a href="https://msdn.microsoft.com/library/windows/hardware/jj938062">PNP_SERIAL_BUS_DESCRIPTOR</a> structure to enable drivers to access the values in this descriptor.</p>

<p>An SPB controller driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450926">SpbTargetGetConnectionParameters</a> method to get the connection parameters for a target device on a <a href="https://msdn.microsoft.com/2c660e14-5b27-4610-a328-735b07ed0773">simple peripheral bus</a> (typically, I²C or SPI). This method writes the connection parameters to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406204">SPB_CONNECTION_PARAMETERS</a> structure, and the <b>ConnectionParameters</b> member of this structure is a pointer to an <b>RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</b> structure.</p>

<p>For a code example that uses the <b>RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</b> structure, see <a href="https://msdn.microsoft.com/B614993A-0EA9-4B91-A336-80EEF9BE3E69">How to Get the Connection Settings for a Device</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Reshub.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj938062">PNP_SERIAL_BUS_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406204">SPB_CONNECTION_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450926">SpbTargetGetConnectionParameters</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
