---
UID : NS:portcls._PCNOTIFICATION_BUFFER
title : _PCNOTIFICATION_BUFFER
author : windows-driver-content
description : The notification buffer used by IPortClsNotifications.
old-location : audio\pcnotification_buffer.htm
old-project : audio
ms.assetid : EEE091E4-29D1-4C6F-B543-C54736660CCA
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _PCNOTIFICATION_BUFFER, PCNOTIFICATION_BUFFER, *PPCNOTIFICATION_BUFFER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : portcls.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1703
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PCNOTIFICATION_BUFFER
req.alt-loc : Portcls.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : PCNOTIFICATION_BUFFER, *PPCNOTIFICATION_BUFFER
---

# _PCNOTIFICATION_BUFFER structure
The notification buffer used by <a href="..\portcls\nn-portcls-iportclsnotifications.md">IPortClsNotifications</a>.

## Syntax
````
typedef struct _PCNOTIFICATION_BUFFER {
  UCHAR NotificationBuffer[1];
} PCNOTIFICATION_BUFFER, *PPCNOTIFICATION_BUFFER;
````

## Members

        
            `NotificationBuffer`

            The notification buffer used by <a href="..\portcls\nn-portcls-iportclsnotifications.md">IPortClsNotifications</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h |

    ## See Also

        <dl>
<dt>
<a href="..\portcls\nn-portcls-iportclsnotifications.md">IPortClsNotifications</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PCNOTIFICATION_BUFFER structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>