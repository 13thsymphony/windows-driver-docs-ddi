---
UID: NF:pepfx.PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE
title: PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_UART_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_spb_uart_resource.htm
old-project: kernel
ms.assetid: C1018E89-D3EC-49A0-B02E-254378000378
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE
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
req.alt-api: PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE
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
req.typenames: PEP_WORK_TYPE, *PPEP_WORK_TYPE
---

# PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function



## -description
The <b>PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_uart_resource.md">PEP_ACPI_SPB_UART_RESOURCE</a> structure.



## -syntax

````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE(
  _In_  ULONG              BaudRate,
  _In_  UCHAR              BitsPerByte,
  _In_  UCHAR              StopBits,
  _In_  UCHAR              LinesInUse,
  _In_  UCHAR              IsBigEndian,
  _In_  UCHAR              Parity,
  _In_  UCHAR              FlowControl,
  _In_  USHORT             RxSize,
  _In_  USHORT             TxSize,
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

### -param BaudRate [in]

Specifies the baud rate of the connection.


### -param BitsPerByte [in]

Specifies the number of bits per byte of data.


### -param StopBits [in]

Specifies the stop bits used in the connection.


### -param LinesInUse [in]

Flag indicating the serial lines that are enabled. A value of 1 in the bit positions indicates that the line is enabled.

<table>
<tr>
<th>Bit</th>
<th>Meaning</th>
</tr>
<tr>

### -param 0

</td>
<td width="60%">
This bit is reserved and must be set to zero.

</td>
</tr>
<tr>

### -param 1

</td>
<td width="60%">
This bit is reserved and must be set to zero.

</td>
</tr>
<tr>

### -param 2

</td>
<td width="60%">
Data Carrier Detect (DTD)

</td>
</tr>
<tr>

### -param 3

</td>
<td width="60%">
Ring Indicator (RI)

</td>
</tr>
<tr>

### -param 4

</td>
<td width="60%">
Data Set Ready (DSR)

</td>
</tr>
<tr>

### -param 5

</td>
<td width="60%">
Data Terminal Ready (DTR)

</td>
</tr>
<tr>

### -param 6

</td>
<td width="60%">
Clear to Send (CTS)

</td>
</tr>
<tr>

### -param 7

</td>
<td width="60%">
Request to Send (RTS)

</td>
</tr>
</table>
 


### -param IsBigEndian [in]

Indicates if the most significant bits of data are in the lowest address. 


### -param Parity [in]

Specifies the parity of the connection.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">

### -param 0x00

</td>
<td width="60%">
None

</td>
</tr>
<tr>
<td width="40%">

### -param 0x01

</td>
<td width="60%">
Even

</td>
</tr>
<tr>
<td width="40%">

### -param 0x02

</td>
<td width="60%">
Odd

</td>
</tr>
<tr>
<td width="40%">

### -param 0x03

</td>
<td width="60%">
Mark

</td>
</tr>
<tr>
<td width="40%">

### -param 0x04

</td>
<td width="60%">
Space

</td>
</tr>
</table>
 


### -param FlowControl [in]

Specifies the type of flow control used by the connection.


### -param RxSize [in]

Specifies the maximum receive buffer size, in bytes, that is supported by this connection.


### -param TxSize [in]

Specifies the maximum transmit buffer size, in bytes, that is supported by this connection.


### -param ResourceSource [in]

The name of the serial bus controller device to which this
connection descriptor applies. The name can be a fully
qualified path, a relative path, or a simple name segment
that utilizes the namespace search rules.


### -param ResourceSourceIndex [in]

This parameter should always be zero.


### -param ResourceUsage [in]

Indicates if this resource is in use.


### -param SharedMode [in]

Indicates if this resource is shared.


### -param VendorData [in]

A pointer to optional data that is specific to the serial bus connection type.


### -param VendorDataLength [in]

The length of the buffer pointed to by the <i>VendorData</i> parameter.


### -param Resource [out]

A pointer to the resource. The structure behind the pointer is of type <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_uart_resource.md">PEP_ACPI_SPB_UART_RESOURCE</a>.


## -returns
This function does not return a value.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_acpi_spb_uart_resource.md">PEP_ACPI_SPB_UART_RESOURCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

