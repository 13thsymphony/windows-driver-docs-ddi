---
UID: NF.storport.StorPortGetStartIoPerfParams
title: StorPortGetStartIoPerfParams function
author: windows-driver-content
description: The StorPortGetStartIoPerfParams routine places the performance parameters for a given I/O request in a STARTIO_PERFORMANCE_PARAMETERS structure.
old-location: storage\storportgetstartioperfparams.htm
old-project: storage
ms.assetid: c3314ac6-2b46-417f-a87b-64e27df9686d
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: StorPortGetStartIoPerfParams
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortGetStartIoPerfParams
req.alt-loc: storport.h
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
req.product: Windows 10 or later.
---

# StorPortGetStartIoPerfParams function



## -description
The <b>StorPortGetStartIoPerfParams</b> routine places the performance parameters for a given I/O request in a <a href="storage.startio_performance_parameters">STARTIO_PERFORMANCE_PARAMETERS</a> structure.



## -syntax

````
ULONG StorPortGetStartIoPerfParams(
  _In_    PVOID                           HwDeviceExtension,
  _In_    PSCSI_REQUEST_BLOCK             Srb,
  _Inout_ PSTARTIO_PERFORMANCE_PARAMETERS StartIoPerfParams
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

The SRB pointer that was passed in to the  <a href="storage.hwstorstartio">HwStorStartIo</a> routine that was supplied by the miniport driver. This parameter must not be <b>NULL</b>.


### -param StartIoPerfParams [in, out]

A pointer to a STARTIO_PERFORMANCE_PARAMETERS structure that the miniport driver supplies.  The miniport driver needs to set only the size of the allocated structure, as Storport will set the other members. This parameter must not be <b>NULL</b>.


## -returns
StorPortGetStartIoPerfParams returns one of the following status values:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>Indicates that the performance parameters have been stored in <i>StartIoPerfParams</i>.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>Either the <i>Srb</i> parameter or the <i>StartIoPerfParams</i> parameter is <b>NULL</b>.

-or-

The <i>HwDeviceExtension</i> parameter is NULL or not valid.

-or-

The <i>Srb</i> parameter is not pointing to an SRB sent by Storport

-or-

The structure pointed to by <i>StartIoPerfParams</i> is not valid because the value of its <b>Size</b> member indicates that structure is too small to contain the returned data.

 


## -remarks
Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="storage.scsi_request_block">SCSI_REQUEST_BLOCK</a> or <a href="storage.storage_request_block">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.


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
Header

</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.scsi_request_block">SCSI_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="storage.startio_performance_parameters">STARTIO_PERFORMANCE_PARAMETERS</a>
</dt>
<dt>
<a href="storage.storage_request_block">STORAGE_REQUEST_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetStartIoPerfParams routine%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

