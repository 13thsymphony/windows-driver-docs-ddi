---
UID: NE:wdm._PCW_CALLBACK_TYPE
title: _PCW_CALLBACK_TYPE
author: windows-driver-content
description: The PCW_CALLBACK_TYPE enumeration defines the notification type to send to the registered provider of the counter set. A provider passes a pointer to this enumeration as a parameter to the PcwCallback function.
old-location: devtest\pcw_callback_type.htm
old-project: devtest
ms.assetid: 92f7a980-509a-44af-b480-fa8c212f4ac6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PCW_CALLBACK_TYPE, *PPCW_CALLBACK_TYPE, PCW_CALLBACK_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCW_CALLBACK_TYPE
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
req.irql: PASSIVE_LEVEL
req.typenames: *PPCW_CALLBACK_TYPE, PCW_CALLBACK_TYPE
req.product: Windows 10 or later.
---

# _PCW_CALLBACK_TYPE Enumeration
The <b>PCW_CALLBACK_TYPE</b> enumeration defines the notification type to send to the registered provider of the counter set. A provider passes a pointer to this enumeration as a parameter to the <a href="..\wdm\nc-wdm-pcw_callback.md">PcwCallback</a> function.

## Syntax
````
typedef enum _PCW_CALLBACK_TYPE { 
  PcwCallbackAddCounter          = 0,
  PcwCallbackRemoveCounter       = 1,
  PcwCallbackEnumerateInstances  = 2,
  PcwCallbackCollectData         = 3
} PCW_CALLBACK_TYPE, *PPCW_CALLBACK_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>PcwCallbackAddCounter</td>
                    <td>The provider is asked to add an instance of the counter set.</td>
                </tr>
            
                <tr>
                    <td>PcwCallbackCollectData</td>
                    <td>The provider is asked to collect data from an instance of the counter set.</td>
                </tr>
            
                <tr>
                    <td>PcwCallbackEnumerateInstances</td>
                    <td>The provider is asked to enumerate instances of the counter set.</td>
                </tr>
            
                <tr>
                    <td>PcwCallbackRemoveCounter</td>
                    <td>The provider is asked to remove an instance of the counter set.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |

## See Also

<dl>
<dt>
<a href="..\wdm\nc-wdm-pcw_callback.md">PcwCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20PCW_CALLBACK_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>