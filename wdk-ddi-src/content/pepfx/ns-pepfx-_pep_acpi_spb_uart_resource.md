---
UID : NS:pepfx._PEP_ACPI_SPB_UART_RESOURCE
title : _PEP_ACPI_SPB_UART_RESOURCE
author : windows-driver-content
description : The PEP_ACPI_SPB_UART_RESOURCE structure describes an ACPI UART serial bus resource.
old-location : kernel\pep_acpi_spb_uart_resource.htm
old-project : kernel
ms.assetid : 3E8C7E47-EFCD-4261-9258-61C6A262287A
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : 5, PPEP_ACPI_SPB_UART_RESOURCE structure pointer [Kernel-Mode Driver Architecture], PEP_ACPI_SPB_UART_RESOURCE, PPEP_ACPI_SPB_UART_RESOURCE, _PEP_ACPI_SPB_UART_RESOURCE, *PPEP_ACPI_SPB_UART_RESOURCE, 3, pepfx/PEP_ACPI_SPB_UART_RESOURCE, 0, 1, 7, 2, 6, kernel.pep_acpi_spb_uart_resource, 4, pepfx/PPEP_ACPI_SPB_UART_RESOURCE, PEP_ACPI_SPB_UART_RESOURCE structure [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : pepfx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PEP_ACPI_SPB_UART_RESOURCE, *PPEP_ACPI_SPB_UART_RESOURCE
---

# _PEP_ACPI_SPB_UART_RESOURCE structure
The <b>PEP_ACPI_SPB_UART_RESOURCE</b> structure describes an ACPI UART serial bus resource.

## Syntax
````
typedef struct _PEP_ACPI_SPB_UART_RESOURCE {
  PEP_ACPI_SPB_RESOURCE SpbCommon;
  ULONG                 BaudRate;
  USHORT                RxBufferSize;
  USHORT                TxBufferSize;
  UCHAR                 Parity;
  UCHAR                 LinesInUse;
} PEP_ACPI_SPB_UART_RESOURCE, *PPEP_ACPI_SPB_UART_RESOURCE;
````

## Members


`BaudRate`

The baud rate of the connection.

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

`Parity`

Indicates the parity of the connection.
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

`RxBufferSize`

The maximum receive buffer size, in bytes, that is supported by this connection.

`SpbCommon`

A <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_resource.md">PEP_ACPI_SPB_RESOURCE</a> structure describing this resource.

`TxBufferSize`

The maximum transmit buffer size, in bytes, that is supported by this connection.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_acpi_spb_resource.md">PEP_ACPI_SPB_RESOURCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_SPB_UART_RESOURCE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>