---
UID: NF.mcd.ChangerInitialize
title: ChangerInitialize function
author: windows-driver-content
description: ChangerInitialize readies the changer to receive other requests.
old-location: storage\changerinitialize.htm
old-project: storage
ms.assetid: 7cb90d35-53e5-4c73-a1f5-9fc3f99cf1b2
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ChangerInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ChangerInitialize
req.alt-loc: mcd.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# ChangerInitialize function



## -description
<b>ChangerInitialize</b> readies the changer to receive other requests. 


## -syntax

````
NTSTATUS ChangerInitialize(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the device object created by the changer class driver to represent this changer. 

## -returns
<b>ChangerInitialize</b> returns the STATUS_<i>XXX</i> value returned by the system port driver or one of the following values:
      

STATUS_SUCCESS

STATUS_INSUFFICIENT_RESOURCES

## -remarks
The changer class driver calls <b>ChangerInitialize</b> during driver initialization, after creating a device object to represent a changer. 

<b>ChangerInitialize</b> performs any device-specific processing required to get the changer ready to receive requests. It also typically stores device-specific information in the device extension, such as SCSI inquiry data or the non-SCSI equivalent and offsets to generate zero-based element addresses, which are used by the system to refer to changer elements.

After <b>ChangerInitialize</b> returns, the changer miniclass driver and the changer should be able to handle any other request. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Mcd.h (include Mcd.h or Ntddchgr.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.changeradditionalextensionsize">ChangerAdditionalExtensionSize</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerInitialize function%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
