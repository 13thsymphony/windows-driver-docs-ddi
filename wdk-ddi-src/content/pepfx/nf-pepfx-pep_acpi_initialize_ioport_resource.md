---
UID: NF.pepfx.PEP_ACPI_INITIALIZE_IOPORT_RESOURCE
title: PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_ioport_resource.htm
old-project: kernel
ms.assetid: E7F9F8EF-3FDC-41D9-BB89-9EB93ED1A504
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: PEP_ACPI_INITIALIZE_IOPORT_RESOURCE
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
req.alt-api: PEP_ACPI_INITIALIZE_IOPORT_RESOURCE
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

# PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function



## -description
The <b>PEP_ACPI_INITIALIZE_IOPORT_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="kernel.pep_acpi_io_memory_resource">PEP_ACPI_IO_MEMORY_RESOURCE</a> structure.



## -syntax

````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_IOPORT_RESOURCE(
  _In_  UCHAR              Decode,
  _In_  USHORT             MinimumAddress,
  _In_  USHORT             MaximumAddress,
  _In_  UCHAR              Alignment,
  _In_  UCHAR              PortLength,
  _Out_ PPEP_ACPI_RESOURCE Resource
);
````


## -parameters

### -param Decode [in]

Specifies how to decode the resource address. If bit 0 is a 1, this indicates that the logical device decodes 16-bit addresses. If bit 0 is 0, this indicates that the logical device only decodes the first 10 bits of the address.

Bits 1 to 7 of this parameter are reserved and must be set to zero.


### -param MinimumAddress [in]

Specifies the minimum acceptable starting address for the IO range.


### -param MaximumAddress [in]

Specifies the maximum acceptable starting address for the IO range.


### -param Alignment [in]

Specifies the alignment granularity for the IO address assigned.


### -param PortLength [in]

Specifies the number of bytes in the IO range.


### -param Resource [out]

A pointer to the resource. The structure behind the pointer is of type <a href="kernel.pep_acpi_io_memory_resource">PEP_ACPI_IO_MEMORY_RESOURCE</a>.


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
<a href="kernel.pep_acpi_io_memory_resource">PEP_ACPI_IO_MEMORY_RESOURCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

