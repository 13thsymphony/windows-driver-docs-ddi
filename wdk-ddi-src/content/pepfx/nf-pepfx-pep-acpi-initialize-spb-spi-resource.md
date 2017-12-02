---
UID: NF.pepfx.PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE
title: PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_SPI_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_spb_spi_resource.htm
old-project: kernel
ms.assetid: 76568167-283C-4966-B7FC-0E8CDCD19B60
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE
req.alt-loc: pepfx.h
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
---

# PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function



## -description
<p>The <b>PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx--pep-acpi-spb-spi-resource.md">PEP_ACPI_SPB_SPI_RESOURCE</a> structure.</p>


## -syntax

````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE(
  _In_  USHORT             DeviceSelection,
  _In_  UCHAR              DeviceSelectionPolarity,
  _In_  UCHAR              WireMode,
  _In_  UCHAR              DataBitLength,
  _In_  BOOLEAN            SlaveMode,
  _In_  ULONG              ConnectionSpeed,
  _In_  UCHAR              ClockPolarity,
  _In_  UCHAR              ClockPhase,
  _In_  PUNICODE_STRING    ResourceSource,
  _In_  UCHAR              ResourceSourceIndex,
  _In_  BOOLEAN            ResourceUsage,
  _In_  BOOLEAN            SharedMode,
  _In_  PCHAR              VendorData,
  _In_  USHORT             VendorDataLength,
  _Out_ PPEP_ACPI_RESOURCE Resource
);
````


## -parameters
<dl>

### -param DeviceSelection [in]

<dd>
<p>The device selection value. This value is
specific to the device and may refer to a chip-select line, GPIO
line, or other line selection mechanism.</p>
</dd>

### -param DeviceSelectionPolarity [in]

<dd>
<p>The polarity of the clock. If zero, this indicates the
clock is low during the first phase. If 1, this indicates the
clock is high during the first phase.</p>
</dd>

### -param WireMode [in]

<dd>
<p>When zero, indicates that this device produces and consumes this resource. Otherwise, this device only consumes this resource.</p>
</dd>

### -param DataBitLength [in]

<dd>
<p>The size, in bits, of the smallest unit of transfer.</p>
</dd>

### -param SlaveMode [in]

<dd>
<p>Indicates if the resource is operating in slave mode.</p>
</dd>

### -param ConnectionSpeed [in]

<dd>
<p>The maximum speed, in hertz, supported by this connection.</p>
</dd>

### -param ClockPolarity [in]

<dd>
<p>The polarity of the clock. If zero, this indicates the
clock is low during the first phase. If 1, this indicates the
clock is high during the first phase.</p>
</dd>

### -param ClockPhase [in]

<dd>
<p>The phase of the clock pulse on which to capture data.</p>
</dd>

### -param ResourceSource [in]

<dd>
<p>The name of the serial bus controller device to which this
connection descriptor applies. The name can be a fully
qualified path, a relative path, or a simple name segment
that utilizes the namespace search rules.</p>
</dd>

### -param ResourceSourceIndex [in]

<dd>
<p>This parameter should always be set to zero.</p>
</dd>

### -param ResourceUsage [in]

<dd>
<p>Indicates if the resource is in use.</p>
</dd>

### -param SharedMode [in]

<dd>
<p>Indicates if the resource is shared.</p>
</dd>

### -param VendorData [in]

<dd>
<p>A pointer to optional data that is specific to the serial bus connection type.</p>
</dd>

### -param VendorDataLength [in]

<dd>
<p>The length of the buffer pointed to by the <i>VendorData</i> parameter.</p>
</dd>

### -param Resource [out]

<dd>
<p>A pointer to the resource. The structure behind the pointer is of type <a href="..\pepfx\ns-pepfx--pep-acpi-spb-spi-resource.md">PEP_ACPI_SPB_SPI_RESOURCE</a>.</p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\pepfx\ns-pepfx--pep-acpi-spb-spi-resource.md">PEP_ACPI_SPB_SPI_RESOURCE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
