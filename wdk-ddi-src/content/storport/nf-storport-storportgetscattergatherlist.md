---
UID: NF.storport.StorPortGetScatterGatherList
title: StorPortGetScatterGatherList function
author: windows-driver-content
description: The StorPortGetScatterGatherList routine retrieves the associated scatter/gather list for the specified SCSI request block (SRB).
old-location: storage\storportgetscattergatherlist.htm
old-project: storage
ms.assetid: ddb7052d-b9f3-40f6-b00a-6bf52f010cdc
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: StorPortGetScatterGatherList
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
req.alt-api: StorPortGetScatterGatherList
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
req.irql: 
req.product: Windows 10 or later.
---

# StorPortGetScatterGatherList function



## -description
The <b>StorPortGetScatterGatherList</b> routine retrieves the associated scatter/gather list for the specified SCSI request block (SRB). 



## -syntax

````
STORPORT_API PSTOR_SCATTER_GATHER_LIST StorPortGetScatterGatherList(
  _In_ PVOID               HwDeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK Srb
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport immediately after the miniport driver calls <a href="storage.storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param Srb [in]

Pointer to the SRB for which the scatter gather list is to be constructed. 


## -returns
<b>StorPortGetScatterGatherList</b> returns a pointer to the scatter/gather list. 


## -remarks
This routine is provided with the Storport driver library. There is no parallel routine provided in the SCSI port library. 

The pointer to the scatter/gather list that is returned is valid only until the SRB is completed. 

The miniport driver does not have to free the memory for the scatter/gather list that <b>StorPortGetScatterGatherList</b> returns. 

The miniport driver must not modify the scatter/gather list.

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
</table>

## -see-also
<dl>
<dt>
<a href="storage.scsi_request_block">SCSI_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="storage.storage_request_block">STORAGE_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="storage.stor_scatter_gather_element">STOR_SCATTER_GATHER_ELEMENT</a>
</dt>
<dt>
<a href="storage.stor_scatter_gather_list">STOR_SCATTER_GATHER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetScatterGatherList routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

