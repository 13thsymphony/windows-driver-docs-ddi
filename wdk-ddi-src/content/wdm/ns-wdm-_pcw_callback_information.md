---
UID: NS.WDM._PCW_CALLBACK_INFORMATION
title: _PCW_CALLBACK_INFORMATION
author: windows-driver-content
description: The PCW_CALLBACK_INFORMATION union supplies details about the notification to send. A provider passes a pointer to this union as a parameter to the PcwCallback function.
old-location: devtest\pcw_callback_information.htm
old-project: devtest
ms.assetid: cc1882a9-eba7-494c-9047-5c97b1e3c19b
ms.author: windowsdriverdev
ms.date: 11/21/2017
ms.keywords: _PCW_CALLBACK_INFORMATION, PCW_CALLBACK_INFORMATION, *PPCW_CALLBACK_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCW_CALLBACK_INFORMATION
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _PCW_CALLBACK_INFORMATION structure



## -description
The <b>PCW_CALLBACK_INFORMATION</b> union supplies details about the notification to send. A provider passes a pointer to this union as a parameter to the <a href="..\wdm\nc-wdm-pcw_callback.md">PcwCallback</a> function. 


## -syntax

````
typedef union _PCW_CALLBACK_INFORMATION {
  PCW_COUNTER_INFORMATION AddCounter;
  PCW_COUNTER_INFORMATION RemoveCounter;
  PCW_MASK_INFORMATION    EnumerateInstances;
  PCW_MASK_INFORMATION    CollectData;
} PCW_CALLBACK_INFORMATION, *PPCW_CALLBACK_INFORMATION;
````


## -struct-fields

### -field AddCounter

The PCW_COUNTER_INFORMATION structure that identifies the counter being added. 

### -field RemoveCounter

The PCW_COUNTER_INFORMATION structure that identifies the counter being removed. 

### -field EnumerateInstances

The PCW_MASK_INFORMATION structure that identifies the instances of the counter set.

### -field CollectData

The PCW_MASK_INFORMATION structure that identifies the instance of the counter set and its buffer.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h or Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="devtest.pcw_counter_information">PCW_COUNTER_INFORMATION</a>
</dt>
<dt>
<a href="devtest.pcw_mask_information">PCW_MASK_INFORMATION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20PCW_CALLBACK_INFORMATION union%20 RELEASE:%20(11/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
