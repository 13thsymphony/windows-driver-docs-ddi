---
UID: NC:ntdddump.DUMP_READ
title: DUMP_READ
author: windows-driver-content
description: The Dump_Read callback routine is called after the read from the dump port driver. The filter driver can access the dump data during the call to this routine.
old-location: storage\dump_read.htm
old-project: storage
ms.assetid: 5F95D38C-8E11-49D4-82C4-718BD846A834
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.dump_read, Dump_Read routine [Storage Devices], Dump_Read, PDUMP_READ, PDUMP_READ, ntdddump/Dump_Read
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntdddump.h
req.include-header: Ntdddump.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8
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
-	UserDefined
apilocation:
-	ntdddump.h
apiname:
-	Dump_Read
product: Windows
targetos: Windows
req.typenames: VERIFY_INFORMATION, *PVERIFY_INFORMATION
---


# DUMP_READ callback function
The <i>Dump_Read</i> callback routine is called after the read from the dump port driver. The filter driver can access the dump data during the call to this routine.

## Syntax

```
DUMP_READ DumpRead;

NTSTATUS DumpRead(
  PFILTER_EXTENSION FilterExtension,
  PLARGE_INTEGER DiskByteOffset,
  PMDL Mdl
)
{...}
```

## Parameters

`FilterExtension`

A pointer to a <a href="..\ntdddump\ns-ntdddump-_filter_extension.md">FILTER_EXTENSION</a> structure.

`DiskByteOffset`

The value, in bytes, relative to the source partition for the crash dump or hibernation. Filter drivers should not modify this field.

`Mdl`

A pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure that describes the data buffer containing the dump data. Filter drivers should not modify this field.


## Return Value

If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in <i>Ntstatus.h</i>.

## Remarks

Filter drivers can read the data that was read by the crashdump process. 

Filter drivers can modify the contents of the data buffer contained in <b>Mdl</b> to revert any changes made to the data when it was written to disk.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8 Available starting with Windows 8 |
| **Target Platform** | Desktop |
| **Header** | ntdddump.h (include Ntdddump.h) |

## See Also

<a href="..\ntdddump\nc-ntdddump-dump_write.md">Dump_Write</a>



<a href="..\ntdddump\ns-ntdddump-_filter_extension.md">FILTER_EXTENSION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20Dump_Read routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>