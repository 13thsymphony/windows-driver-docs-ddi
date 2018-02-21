---
UID: NE:ntddk._BDCB_CLASSIFICATION
title: "_BDCB_CLASSIFICATION"
author: windows-driver-content
description: The BDCB_CLASSIFICATION enumeration lists different classifications of boot start images.
old-location: kernel\bdcb_classification.htm
old-project: kernel
ms.assetid: 01627E7A-460F-4E49-B98C-0FCCFAB2F8BB
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/BDCB_CLASSIFICATION, BdCbClassificationKnownBadImageBootCritical, ntddk/BdCbClassificationKnownBadImage, BdCbClassificationKnownBadImage, ntddk/BdCbClassificationEnd, _BDCB_CLASSIFICATION, BdCbClassificationUnknownImage, *PBDCB_CLASSIFICATION, ntddk/BdCbClassificationKnownGoodImage, kernel.bdcb_classification, BDCB_CLASSIFICATION, BDCB_CLASSIFICATION enumeration [Kernel-Mode Driver Architecture], ntddk/BdCbClassificationKnownBadImageBootCritical, BdCbClassificationKnownGoodImage, ntddk/BdCbClassificationUnknownImage, BdCbClassificationEnd
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	BDCB_CLASSIFICATION
product: Windows
targetos: Windows
req.typenames: "*PBDCB_CLASSIFICATION, BDCB_CLASSIFICATION"
---

# _BDCB_CLASSIFICATION Enumeration
The BDCB_CLASSIFICATION enumeration lists different classifications of boot start images.

## Syntax
````
typedef enum _BDCB_CLASSIFICATION { 
  BdCbClassificationUnknownImage,
  BdCbClassificationKnownGoodImage,
  BdCbClassificationKnownBadImage,
  BdCbClassificationKnownBadImageBootCritical,
  BdCbClassificationEnd
} BDCB_CLASSIFICATION;
````

## Constants

<table>
            
                <tr>
                    <td>BdCbClassificationEnd</td>
                    <td>Do not use. Reserved for future use.</td>
                </tr>
            
                <tr>
                    <td>BdCbClassificationKnownBadImage</td>
                    <td>The boot start image has been inspected by anti-malware and found to be malware.</td>
                </tr>
            
                <tr>
                    <td>BdCbClassificationKnownBadImageBootCritical</td>
                    <td>The boot start image has been inspected by anti-malware and found to be malware, but the anti-malware boot-start driver also knows it to be critical to the success of the boot.</td>
                </tr>
            
                <tr>
                    <td>BdCbClassificationKnownGoodImage</td>
                    <td>The boot start image has been inspected by anti-malware and found not to be malware.</td>
                </tr>
            
                <tr>
                    <td>BdCbClassificationUnknownImage</td>
                    <td>The boot start image has not been inspected by anti-malware or anti-malware does not have enough information to determine whether the binary is malware.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with  Windows 8. Available starting with  Windows 8. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ns-ntddk-_bdcb_image_information.md">BDCB_IMAGE_INFORMATION</a>



<a href="..\ntddk\nf-ntddk-ioregisterbootdrivercallback.md">BOOT_DRIVER_CALLBACK_FUNCTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BDCB_CLASSIFICATION enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>