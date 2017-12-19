---
UID: NF.sercx.SerCxRetrieveTransmitMdl
title: SerCxRetrieveTransmitMdl function
author: windows-driver-content
description: The SerCxRetrieveTransmitMdl method retrieves the MDL that describes the buffer that contains the next block of output data to be transmitted.
old-location: serports\sercxretrievetransmitmdl.htm
old-project: serports
ms.assetid: C0FF3667-9641-4032-826E-7E297F57CDFA
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCxRetrieveTransmitMdl
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
req.alt-api: SerCxRetrieveTransmitMdl
req.alt-loc: 1.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# SerCxRetrieveTransmitMdl function



## -description
The <b>SerCxRetrieveTransmitMdl</b> method retrieves the MDL that describes the buffer that contains the next block of output data to be transmitted.



## -syntax

````
NTSTATUS SerCxRetrieveTransmitMdl(
  [in]  WDFDEVICE Device,
  [out] PMDL      *Mdl
);
````


## -parameters

### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param Mdl [out]

A pointer to a location into which the method writes a pointer to the MDL.


## -returns
<b>SerCxRetrieveTransmitMdl</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>This value is returned if one of the following occurs:

 


## -remarks
The serial controller driver calls this function to obtain an MDL to use for the current transmit (write) operation. The MDL describes the buffer memory from which the driver is to obtain the data to be transmitted. The driver is the exclusive owner of this MDL until it calls the <a href="serports.sercxprogresstransmit">SerCxProgressTransmit</a> method, after which the MDL pointer is invalid and the driver must no longer try to access either the MDL or the buffer memory that the MDL describes.

For more information about MDLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>1.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="serports.sercxprogresstransmit">SerCxProgressTransmit</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxRetrieveTransmitMdl method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

