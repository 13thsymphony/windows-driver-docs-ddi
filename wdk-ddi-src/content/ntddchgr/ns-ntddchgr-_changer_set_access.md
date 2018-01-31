---
UID : NS:ntddchgr._CHANGER_SET_ACCESS
title : "_CHANGER_SET_ACCESS"
author : windows-driver-content
description : The CHANGER_SET_ACCESS structure is used in conjunction with theIOCTL_CHANGER_SET_ACCESS request to set the state of the device's import/export port (IEport), door, or keypad.
old-location : storage\changer_set_access.htm
old-project : storage
ms.assetid : 4349d772-89c6-4201-9d9d-2e0590d61424
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : structs-changer_01f5a159-3d46-4400-8eae-87367e81ed72.xml, CHANGER_SET_ACCESS, ntddchgr/CHANGER_SET_ACCESS, ntddchgr/PCHANGER_SET_ACCESS, PCHANGER_SET_ACCESS structure pointer [Storage Devices], PCHANGER_SET_ACCESS, *PCHANGER_SET_ACCESS, _CHANGER_SET_ACCESS, storage.changer_set_access, CHANGER_SET_ACCESS structure [Storage Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddchgr.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : CHANGER_SET_ACCESS, *PCHANGER_SET_ACCESS
---

# _CHANGER_SET_ACCESS structure
The CHANGER_SET_ACCESS structure is used in conjunction with the<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_set_access.md">IOCTL_CHANGER_SET_ACCESS</a> request to set the state of the device's import/export port (IEport), door, or keypad.

## Syntax
````
typedef struct _CHANGER_SET_ACCESS {
  CHANGER_ELEMENT Element;
  ULONG           Control;
} CHANGER_SET_ACCESS, *PCHANGER_SET_ACCESS;
````

## Members


`Control`

Specifies the operation to perform on the element. The <b>Features0</b> member of <a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a> indicates whether the changer supports a particular category of operation.




#### LOCK_ELEMENT

Lock the door, IEport, or keypad. Valid only if CHANGER_LOCK_UNLOCK is set.


#### UNLOCK_ELEMENT

Unlock the door, IEport, or keypad. Valid only if CHANGER_LOCK_UNLOCK is set.


#### EXTEND_IEPORT

Extend the IEport. Valid only if CHANGER_OPEN_IEPORT is set.


#### RETRACT_IEPORT

Retract the IEport. Valid only if CHANGER_CLOSE_IEPORT is set.

`Element`

Contains a <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a> structure that specifies the element type and the zero-based address of the element to set. The <b>ElementType</b> member of the CHANGER_ELEMENT structure must be assigned one of the following values:

<b>ChangerIEPortChangerDoorChangerKeypad</b>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddchgr.h |

## See Also

<a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>

<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_set_access.md">IOCTL_CHANGER_SET_ACCESS</a>

<a href="..\mcd\nf-mcd-changersetaccess.md">ChangerSetAccess</a>

<a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_SET_ACCESS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>