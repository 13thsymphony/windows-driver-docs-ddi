---
UID: NF.storport.StorPortGetDataInBufferSystemAddress
title: StorPortGetDataInBufferSystemAddress function
author: windows-driver-content
description: Returns the system address for the input data buffer of a SCSI request block (SRB).
old-location: storage\storportgetdatainbuffersystemaddress.htm
old-project: storage
ms.assetid: 3FA48004-E96A-4ED7-935F-B7F58A74FB1F
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: StorPortGetDataInBufferSystemAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortGetDataInBufferSystemAddress
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# StorPortGetDataInBufferSystemAddress function



## -description
Returns the system address for the input data buffer  of a SCSI request block (SRB).



## -syntax

````
ULONG StorPortGetDataInBufferSystemAddress(
  _In_  PVOID               HwDeviceExtension,
  _In_  PSCSI_REQUEST_BLOCK Srb,
  _Out_ PVOID               *SystemAddress
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

The request block to containing the input data buffer.


### -param SystemAddress [out]

A pointer to  a an  address  value to receive the system address for the input data buffer in <i>Srb</i>.


## -returns
A status value indicating the result of the notification. This can be one of these values:
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>A system address of the input data buffer for <i>Srb</i> was successfully returned.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The pointer value in <i>SystemAddress</i> is NULL.
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>The current IRQL is &gt; DISPATCH_LEVEL.
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A system address can not be assigned.

 


## -remarks


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
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Storport.lib</dt>
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
<a href="storage.storportgetdatainbuffermdl">StorPortGetDataInBufferMdl</a>
</dt>
<dt>
<a href="storage.storportgetdatainbufferscattergatherlist">StorPortGetDataInBufferScatterGatherList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetDataInBufferSystemAddress routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

