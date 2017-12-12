---
UID: NE.ntddk._BDCB_CLASSIFICATION
title: _BDCB_CLASSIFICATION
author: windows-driver-content
description: The BDCB_CLASSIFICATION enumeration lists different classifications of boot start images.
old-location: kernel\bdcb_classification.htm
old-project: kernel
ms.assetid: 01627E7A-460F-4E49-B98C-0FCCFAB2F8BB
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _BDCB_CLASSIFICATION, BDCB_CLASSIFICATION, *PBDCB_CLASSIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDCB_CLASSIFICATION
req.alt-loc: ntddk.h
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
---

# _BDCB_CLASSIFICATION enumeration



## -description
The BDCB_CLASSIFICATION enumeration lists different classifications of boot start images.



## -syntax

````
typedef enum _BDCB_CLASSIFICATION { 
  BdCbClassificationUnknownImage,
  BdCbClassificationKnownGoodImage,
  BdCbClassificationKnownBadImage,
  BdCbClassificationKnownBadImageBootCritical,
  BdCbClassificationEnd
} BDCB_CLASSIFICATION;
````


## -enum-fields

### -field BdCbClassificationUnknownImage

The boot start image has not been inspected by anti-malware or anti-malware does not have enough information to determine whether the binary is malware.


### -field BdCbClassificationKnownGoodImage

The boot start image has been inspected by anti-malware and found not to be malware.


### -field BdCbClassificationKnownBadImage

The boot start image has been inspected by anti-malware and found to be malware.


### -field BdCbClassificationKnownBadImageBootCritical

The boot start image has been inspected by anti-malware and found to be malware, but the anti-malware boot-start driver also knows it to be critical to the success of the boot.


### -field BdCbClassificationEnd

Do not use. Reserved for future use.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with  Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.bdcb_image_information">BDCB_IMAGE_INFORMATION</a>
</dt>
<dt>
<a href="kernel.ioregisterbootdrivercallback">BOOT_DRIVER_CALLBACK_FUNCTION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BDCB_CLASSIFICATION enumeration%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

