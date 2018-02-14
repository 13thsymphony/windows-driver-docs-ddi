---
UID: NF:sercx.SerCxRetrieveTransmitMdl
title: SerCxRetrieveTransmitMdl function
author: windows-driver-content
description: The SerCxRetrieveTransmitMdl method retrieves the MDL that describes the buffer that contains the next block of output data to be transmitted.
old-location: serports\sercxretrievetransmitmdl.htm
old-project: serports
ms.assetid: C0FF3667-9641-4032-826E-7E297F57CDFA
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCxRetrieveTransmitMdl method [Serial Ports], 1/SerCxRetrieveTransmitMdl, SerCxRetrieveTransmitMdl, serports.sercxretrievetransmitmdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	1.0\Sercx.h
apiname:
-	SerCxRetrieveTransmitMdl
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---


# SerCxRetrieveTransmitMdl function
The <b>SerCxRetrieveTransmitMdl</b> method retrieves the MDL that describes the buffer that contains the next block of output data to be transmitted.

## Syntax

````
NTSTATUS SerCxRetrieveTransmitMdl(
  [in]  WDFDEVICE Device,
  [out] PMDL      *Mdl
);
````

## Parameters

`Device`

A WDFDEVICE handle to the framework device object that represents the serial controller.

`Mdl`

A pointer to a location into which the method writes a pointer to the MDL.


## Return Value

<b>SerCxRetrieveTransmitMdl</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
This value is returned if one of the following occurs:

<ul>
<li>There is no outstanding transmit request to get an MDL from.</li>
<li>The current number of bytes transmitted (as reported by the <a href="..\sercx\nf-sercx-sercxprogresstransmit.md">SerCxProgressTransmit</a> method) does not equal zero.</li>
<li>The buffer has already been retrieved (and the corresponding call to the <b>SerCxProgressTransmit</b> method has not yet occurred).</li>
<li>The MDL has already been retrieved (and the corresponding call to the <b>SerCxProgressTransmit</b> method has not yet occurred).</li>
</ul>
</td>
</tr>
</table>

## Remarks

The serial controller driver calls this function to obtain an MDL to use for the current transmit (write) operation. The MDL describes the buffer memory from which the driver is to obtain the data to be transmitted. The driver is the exclusive owner of this MDL until it calls the <a href="..\sercx\nf-sercx-sercxprogresstransmit.md">SerCxProgressTransmit</a> method, after which the MDL pointer is invalid and the driver must no longer try to access either the MDL or the buffer memory that the MDL describes.

For more information about MDLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Target Platform** | Universal |
| **Header** | sercx.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\sercx\nf-sercx-sercxprogresstransmit.md">SerCxProgressTransmit</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxRetrieveTransmitMdl method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>