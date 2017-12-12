---
UID: NS.NTDDTAPE._TAPE_WMI_OPERATIONS
title: _TAPE_WMI_OPERATIONS
author: windows-driver-content
description: The tape miniclass driver passes this structure to its TapeMiniWMIControl routine to indicate which WMI operation must be performed by the device.
old-location: storage\tape_wmi_operations.htm
old-project: storage
ms.assetid: 430d982e-4740-46ad-8391-aba5813a833a
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _TAPE_WMI_OPERATIONS, TAPE_WMI_OPERATIONS, *PTAPE_WMI_OPERATIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddtape.h
req.include-header: Ntddchgr.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TAPE_WMI_OPERATIONS
req.alt-loc: ntddtape.h
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

# _TAPE_WMI_OPERATIONS structure



## -description
The tape miniclass driver passes this structure to its <a href="storage.tapeminiwmicontrol">TapeMiniWMIControl</a> routine to indicate which WMI operation must be performed by the device. 



## -syntax

````
typedef struct _TAPE_WMI_OPERATIONS {
  ULONG Method;
  ULONG DataBufferSize;
  PVOID DataBuffer;
} TAPE_WMI_OPERATIONS, *PTAPE_WMI_OPERATIONS;
````


## -struct-fields

### -field Method

Indicates the operation to be performed by the tape device. The operations allowed are as follows:




### -field TAPE_CHECK_FOR_DRIVE_PROBLEM

If the tape drive supports commands to return specific device errors, such as tape alerts, the minidriver's <a href="storage.tapeminiwmicontrol">TapeMiniWMIControl</a> routine should execute the TAPE_QUERY_DEVICE_ERROR_DATA method Otherwise, it should execute the TAPE_QUERY_IO_ERROR_DATA method.

</dd>
</dl>



### -field TAPE_QUERY_DEVICE_ERROR_DATA

Returns specific device errors, such as tape alerts. Not all tape drives support this method.

</dd>
</dl>



### -field TAPE_QUERY_IO_ERROR_DATA  

Returns general I/O error data, such as read/write errors, based on the I/O error count. All tape drives support this method.

</dd>
</dl>

### -field DataBufferSize

Indicates the size in bytes of the buffer in which the tape minidriver returns the results of the operation. 


### -field DataBuffer

Pointer to a buffer in which the tape minidriver returns the results of the operation. The first <b>sizeof</b>(ULONG) bytes of <b>DataBuffer</b> contain a value of type <a href="storage.tape_drive_problem_type">TAPE_DRIVE_PROBLEM_TYPE</a>, followed by <b>DataBufferSize</b> - <b>sizeof</b>(ULONG) bytes of tape data. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddtape.h (include Ntddchgr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.tapeminiwmicontrol">TapeMiniWMIControl</a>
</dt>
<dt>
<a href="storage.tape_drive_problem_type">TAPE_DRIVE_PROBLEM_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_WMI_OPERATIONS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

