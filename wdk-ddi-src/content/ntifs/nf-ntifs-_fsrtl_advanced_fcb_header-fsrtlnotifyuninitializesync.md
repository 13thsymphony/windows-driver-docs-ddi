---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNotifyUninitializeSync
title: FsRtlNotifyUninitializeSync function
author: windows-driver-content
description: The FsRtlNotifyUninitializeSync routine deallocates the synchronization object for a notify list.
old-location: ifsk\fsrtlnotifyuninitializesync.htm
old-project: ifsk
ms.assetid: ac26d5cb-b342-42ec-ad76-23cefe509566
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlNotifyUninitializeSync, FsRtlNotifyUninitializeSync routine [Installable File System Drivers], fsrtlref_bb1d0439-691c-4a2d-8d0f-750f26d75995.xml, ifsk.fsrtlnotifyuninitializesync, ntifs/FsRtlNotifyUninitializeSync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlNotifyUninitializeSync
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlNotifyUninitializeSync function


## -description


The <b>FsRtlNotifyUninitializeSync</b> routine deallocates the synchronization object for a notify list.


## -syntax


````
VOID FsRtlNotifyUninitializeSync(
  _In_ PNOTIFY_SYNC *NotifySync
);
````


## -parameters




### -param NotifySync [in]

A pointer to a location that contains a pointer to the opaque synchronization object.


## -returns



None




## -remarks



The <b>FsRtlNotifyUninitializeSync</b> routine deallocates an opaque synchronization object that was allocated by an earlier call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyinitializesync.md">FsRtlNotifyInitializeSync</a>.




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyinitializesync.md">FsRtlNotifyInitializeSync</a>



 

 

