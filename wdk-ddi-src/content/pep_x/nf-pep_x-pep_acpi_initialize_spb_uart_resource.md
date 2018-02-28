---
UID: NF:pep_x.PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE
title: PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_UART_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_spb_uart_resource.htm
old-project: kernel
ms.assetid: C1018E89-D3EC-49A0-B02E-254378000378
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: 0, 1, 2, 3, 4, 5, 6, 7, PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE, PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_spb_uart_resource, pepfx/PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE
product: Windows
targetos: Windows
req.typenames: PEP_WORK_TYPE, *PPEP_WORK_TYPE, PEP_WORK_TYPE, *PPEP_WORK_TYPE
---


# PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function
The <b>PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_uart_resource.md">PEP_ACPI_SPB_UART_RESOURCE</a> structure.

## Syntax

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

## Parameters

`BaudRate`

Specifies the baud rate of the connection.

`BitsPerByte`

Specifies the number of bits per byte of data.

`StopBits`

Specifies the stop bits used in the connection.

`LinesInUse`

Flag indicating the serial lines that are enabled. A value of 1 in the bit positions indicates that the line is enabled.

<table>
<tr>
<th>Bit</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="0"></a><dl>
<dt><b>0</b></dt>
</dl>
</td>
<td width="60%">
This bit is reserved and must be set to zero.

</td>
</tr>
<tr>
<td width="40%"><a id="1"></a><dl>
<dt><b>1</b></dt>
</dl>
</td>
<td width="60%">
This bit is reserved and must be set to zero.

</td>
</tr>
<tr>
<td width="40%"><a id="2"></a><dl>
<dt><b>2</b></dt>
</dl>
</td>
<td width="60%">
Data Carrier Detect (DTD)

</td>
</tr>
<tr>
<td width="40%"><a id="3"></a><dl>
<dt><b>3</b></dt>
</dl>
</td>
<td width="60%">
Ring Indicator (RI)

</td>
</tr>
<tr>
<td width="40%"><a id="4"></a><dl>
<dt><b>4</b></dt>
</dl>
</td>
<td width="60%">
Data Set Ready (DSR)

</td>
</tr>
<tr>
<td width="40%"><a id="5"></a><dl>
<dt><b>5</b></dt>
</dl>
</td>
<td width="60%">
Data Terminal Ready (DTR)

</td>
</tr>
<tr>
<td width="40%"><a id="6"></a><dl>
<dt><b>6</b></dt>
</dl>
</td>
<td width="60%">
Clear to Send (CTS)

</td>
</tr>
<tr>
<td width="40%"><a id="7"></a><dl>
<dt><b>7</b></dt>
</dl>
</td>
<td width="60%">
Request to Send (RTS)

</td>
</tr>
</table>

`IsBigEndian`

Indicates if the most significant bits of data are in the lowest address.

`Parity`

Specifies the parity of the connection.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x00</dt>
</dl>
</td>
<td width="60%">
None

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x01</dt>
</dl>
</td>
<td width="60%">
Even

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x02</dt>
</dl>
</td>
<td width="60%">
Odd

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x03</dt>
</dl>
</td>
<td width="60%">
Mark

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x04</dt>
</dl>
</td>
<td width="60%">
Space

</td>
</tr>
</table>

`FlowControl`

Specifies the type of flow control used by the connection.

`RxSize`

Specifies the maximum receive buffer size, in bytes, that is supported by this connection.

`TxSize`

Specifies the maximum transmit buffer size, in bytes, that is supported by this connection.

`ResourceSource`

The name of the serial bus controller device to which this
connection descriptor applies. The name can be a fully
qualified path, a relative path, or a simple name segment
that utilizes the namespace search rules.

`ResourceSourceIndex`

This parameter should always be zero.

`ResourceUsage`

Indicates if this resource is in use.

`SharedMode`

Indicates if this resource is shared.

`VendorData`

A pointer to optional data that is specific to the serial bus connection type.

`VendorDataLength`

The length of the buffer pointed to by the <i>VendorData</i> parameter.

`Resource`

A pointer to the resource. The structure behind the pointer is of type <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_uart_resource.md">PEP_ACPI_SPB_UART_RESOURCE</a>.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10.  |
| **Target Platform** | Windows |
| **Header** | pep_x.h (include Pep_x.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_acpi_spb_uart_resource.md">PEP_ACPI_SPB_UART_RESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>