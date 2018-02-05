---
UID : NS:wdm._FILE_IS_REMOTE_DEVICE_INFORMATION
title : "_FILE_IS_REMOTE_DEVICE_INFORMATION"
author : windows-driver-content
description : The FILE_IS_REMOTE_DEVICE_INFORMATION structure is used as an argument to the ZwQueryInformationFile routine.
old-location : kernel\file_is_remote_device_information.htm
old-project : kernel
ms.assetid : E1A82D24-A981-414A-83D8-E71F97E0301A
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : FILE_IS_REMOTE_DEVICE_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_IS_REMOTE_DEVICE_INFORMATION, *PFILE_IS_REMOTE_DEVICE_INFORMATION, PFILE_IS_REMOTE_DEVICE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], kernel.file_is_remote_device_information, wdm/PFILE_IS_REMOTE_DEVICE_INFORMATION, _FILE_IS_REMOTE_DEVICE_INFORMATION, wdm/FILE_IS_REMOTE_DEVICE_INFORMATION, FILE_IS_REMOTE_DEVICE_INFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
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
req.irql : PASSIVE_LEVEL (see Remarks section)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : FILE_IS_REMOTE_DEVICE_INFORMATION, *PFILE_IS_REMOTE_DEVICE_INFORMATION
req.product : Windows 10 or later.
---

# _FILE_IS_REMOTE_DEVICE_INFORMATION structure
The <b>FILE_IS_REMOTE_DEVICE_INFORMATION</b> structure is used as an argument to the <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> routine.

## Syntax
````
typedef struct _FILE_IS_REMOTE_DEVICE_INFORMATION {
  BOOLEAN IsRemote;
} FILE_IS_REMOTE_DEVICE_INFORMATION, *PFILE_IS_REMOTE_DEVICE_INFORMATION;
````

## Members


`IsRemote`

A value that indicates whether the file system that contains the file is a remote file system.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_IS_REMOTE_DEVICE_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>