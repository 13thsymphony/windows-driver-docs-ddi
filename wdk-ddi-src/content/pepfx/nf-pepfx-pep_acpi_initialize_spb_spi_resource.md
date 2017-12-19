---
UID: NF.pepfx.PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE
title: PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_SPI_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_spb_spi_resource.htm
old-project: kernel
ms.assetid: 76568167-283C-4966-B7FC-0E8CDCD19B60
ms.author: windowsdriverdev
ms.date: 12/15/2017
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
---

# PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function



## -description
The <b>PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="kernel.pep_acpi_spb_spi_resource">PEP_ACPI_SPB_SPI_RESOURCE</a> structure.



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

### -param DeviceSelection [in]

The device selection value. This value is
specific to the device and may refer to a chip-select line, GPIO
line, or other line selection mechanism.


### -param DeviceSelectionPolarity [in]

The polarity of the clock. If zero, this indicates the
clock is low during the first phase. If 1, this indicates the
clock is high during the first phase.


### -param WireMode [in]

When zero, indicates that this device produces and consumes this resource. Otherwise, this device only consumes this resource.


### -param DataBitLength [in]

The size, in bits, of the smallest unit of transfer.


### -param SlaveMode [in]

Indicates if the resource is operating in slave mode.


### -param ConnectionSpeed [in]

The maximum speed, in hertz, supported by this connection.


### -param ClockPolarity [in]

The polarity of the clock. If zero, this indicates the
clock is low during the first phase. If 1, this indicates the
clock is high during the first phase.


### -param ClockPhase [in]

The phase of the clock pulse on which to capture data.


### -param ResourceSource [in]

The name of the serial bus controller device to which this
connection descriptor applies. The name can be a fully
qualified path, a relative path, or a simple name segment
that utilizes the namespace search rules.


### -param ResourceSourceIndex [in]

This parameter should always be set to zero.


### -param ResourceUsage [in]

Indicates if the resource is in use.


### -param SharedMode [in]

Indicates if the resource is shared.


### -param VendorData [in]

A pointer to optional data that is specific to the serial bus connection type.


### -param VendorDataLength [in]

The length of the buffer pointed to by the <i>VendorData</i> parameter.


### -param Resource [out]

A pointer to the resource. The structure behind the pointer is of type <a href="kernel.pep_acpi_spb_spi_resource">PEP_ACPI_SPB_SPI_RESOURCE</a>.


## -returns
This function does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

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
<a href="kernel.pep_acpi_spb_spi_resource">PEP_ACPI_SPB_SPI_RESOURCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

