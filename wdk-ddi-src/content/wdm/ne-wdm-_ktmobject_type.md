---
UID: NE.wdm._KTMOBJECT_TYPE
title: _KTMOBJECT_TYPE
author: windows-driver-content
description: The KTMOBJECT_TYPE enumeration identifies the types of objects that KTM supports.
old-location: kernel\ktmobject_type.htm
old-project: kernel
ms.assetid: 0ace1cdf-0a15-48bb-9444-c947239e453e
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _KTMOBJECT_TYPE, KTMOBJECT_TYPE, *PKTMOBJECT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KTMOBJECT_TYPE
req.alt-loc: Wdm.h
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
req.product: Windows 10 or later.
---

# _KTMOBJECT_TYPE enumeration



## -description
The <b>KTMOBJECT_TYPE</b> enumeration identifies the types of objects that KTM supports.



## -syntax

````
typedef enum _KTMOBJECT_TYPE { 
  KTMOBJECT_TRANSACTION          = 0,
  KTMOBJECT_TRANSACTION_MANAGER  = 1,
  KTMOBJECT_RESOURCE_MANAGER     = 2,
  KTMOBJECT_ENLISTMENT           = 3,
  KTMOBJECT_INVALID              = 4
} KTMOBJECT_TYPE, *PKTMOBJECT_TYPE;
````


## -enum-fields

### -field KTMOBJECT_TRANSACTION

KTM transaction objects.


### -field KTMOBJECT_TRANSACTION_MANAGER

KTM transaction manager objects.


### -field KTMOBJECT_RESOURCE_MANAGER

KTM resource manager objects.


### -field KTMOBJECT_ENLISTMENT

KTM enlistment objects.


### -field KTMOBJECT_INVALID

Invalid object type.


## -remarks
The <b>KTMOBJECT_TYPE</b> enumeration is used with the <a href="kernel.zwenumeratetransactionobject">ZwEnumerateTransactionObject</a> routine.

For more information about KTM objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554272">KTM Objects</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later operating system versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.zwenumeratetransactionobject">ZwEnumerateTransactionObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KTMOBJECT_TYPE enumeration%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

