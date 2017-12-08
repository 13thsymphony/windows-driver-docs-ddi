---
UID: NF.storport.StorPortCompleteServiceIrp
title: StorPortCompleteServiceIrp function
author: windows-driver-content
description: The StorPortCompleteServiceIrp routine is called by a Storport virtual miniport driver when it needs to complete a request that it received in its HwStorProcessServiceRequest callback routine.
old-location: storage\storportcompleteserviceirp.htm
old-project: storage
ms.assetid: 359b1096-f987-4884-ab67-2290bf5196b5
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: StorPortCompleteServiceIrp
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
req.alt-api: StorPortCompleteServiceIrp
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

# StorPortCompleteServiceIrp function



## -description
The <b>StorPortCompleteServiceIrp</b> routine is called by a Storport virtual miniport driver when it needs to complete a request that it received in its <a href="storage.hwstorprocessservicerequest">HwStorProcessServiceRequest</a> callback routine.


## -syntax

````
ULONG StorPortCompleteServiceIrp(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID Irp
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the  mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="storage.storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 

### -param Irp [in]

A pointer to the I/O request.

## -returns
<b>StorPortCompleteServiceIrp</b> returns one of the following values:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>Indicates that the routine completed the request successfully.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The Irp that was passed was <b>NULL</b>.

 

## -remarks
The Storport virtual miniport driver's <a href="storage.hwstorprocessservicerequest">HwStorProcessServiceRequest</a> callback routine receives an IRP that is produced by an IOCTL when a caller, such as a user-mode application or kernel-mode driver, requires a reverse callback operation. The I/O is completed by the miniport driver by calling the <b>StorPortCompleteServiceIrp</b> routine when it needs to tell the caller of something or needs the caller to do something.

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
<a href="storage.hwstorprocessservicerequest">HwStorProcessServiceRequest</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortCompleteServiceIrp routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
