---
UID: NC:ntifs.DRIVER_FS_NOTIFICATION
title: DRIVER_FS_NOTIFICATION
author: windows-driver-content
description: A PDRIVER_FS_NOTIFICATION-typed routine is called by the operating system when a file system registers or unregisters itself by using IoRegisterFileSystem or IoUnregisterFileSystem.
old-location: ifsk\pdriver_fs_notification.htm
old-project: ifsk
ms.assetid: 571aaa9b-8620-46ff-af29-19b00804e0ad
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DRIVER_FS_NOTIFICATION, DriverNotificationRoutine, DriverNotificationRoutine routine [Installable File System Drivers], FilterCallbacks_5b421108-0db7-47ba-afba-3a8b79a61d66.xml, ifsk.pdriver_fs_notification, ntifs/DriverNotificationRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ntifs.h
api_name:
-	PDRIVER_FS_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
---


# DRIVER_FS_NOTIFICATION callback function
A PDRIVER_FS_NOTIFICATION-typed routine is called by the operating system when a file system registers or unregisters itself by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548552">IoUnregisterFileSystem</a>.

## Syntax

```
DRIVER_FS_NOTIFICATION DriverFsNotification;

void DriverFsNotification(
  _DEVICE_OBJECT *DeviceObject,
  BOOLEAN FsActive
)
{...}
```

## Parameters

`*DeviceObject`

A pointer to a file system device object for which the notification was called.

`FsActive`

A Boolean value that indicates whether the file system has registered (TRUE) or unregistered (FALSE) itself as an active file system.


## Return Value

This routine does not return a value.

## Remarks

You must declare the callback function by using the <i>DRIVER_FS_NOTIFICATION</i> type. For more information, see the following Example section.


#### Examples

To define a <b>DriverFSNotificationRoutine</b> callback routine that is named <b>MyDriverNotification</b>, you must first provide a function declaration that the Static Driver Verify (SDV) and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DRIVER_FS_NOTIFICATION MyDriverFSNotification;</pre>
</td>
</tr>
</table></span></div>
And then implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyDriverFSNotification (
    __in struct _DEVICE_OBJECT *DeviceObject,
    __in BOOLEAN FsActive
)
{ . . . }</pre>
</td>
</tr>
</table></span></div>
Note that the callback type is declared in <i>Ntifs.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
DRIVER_FS_NOTIFICATION (
  __in struct _DEVICE_OBJECT *DeviceObject,
  __in BOOLEAN FsActive
  );
typedef DRIVER_FS_NOTIFICATION *PDRIVER_FS_NOTIFICATION;</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows 2000 and later versions of the Windows operating system.  |
| **Target Platform** | Desktop |
| **Header** | ntifs.h (include FltKernel.h, Ntifs.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548499">IoRegisterFsRegistrationChange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548508">IoRegisterFsRegistrationChangeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548514">IoRegisterFsRegistrationChangeMountAware</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548557">IoUnregisterFsRegistrationChange</a>