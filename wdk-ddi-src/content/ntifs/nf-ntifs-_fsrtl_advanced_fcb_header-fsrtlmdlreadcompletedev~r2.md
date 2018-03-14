---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlMdlReadCompleteDev~r2
title: FsRtlMdlReadCompleteDev function
author: windows-driver-content
description: The FsRtlMdlReadCompleteDev routine completes the read operation that the FsRtlMdlReadDev routine initiated.
old-location: ifsk\fsrtlmdlreadcompletedev.htm
old-project: ifsk
ms.assetid: 6b48327a-885c-418e-b7d1-c3995642cf1c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlMdlReadCompleteDev, FsRtlMdlReadCompleteDev routine [Installable File System Drivers], fsrtlref_76db9e4c-412e-48a6-b2ae-e6877195dd05.xml, ifsk.fsrtlmdlreadcompletedev, ntifs/FsRtlMdlReadCompleteDev
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlMdlReadCompleteDev
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlMdlReadCompleteDev function


## -description


The <b>FsRtlMdlReadCompleteDev</b> routine completes the read operation that the <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev~r6.md">FsRtlMdlReadDev</a> routine initiated.


## -syntax


````
BOOLEAN FsRtlMdlReadCompleteDev(
  _In_     PFILE_OBJECT   FileObject,
  _In_     PMDL           MdlChain,
  _In_opt_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param FileObject [in]

A pointer to the file object.


### -param MdlChain [in]

On return, a pointer to a linked list of one or more MDLs that point to the cached file data.


### -param DeviceObject [in, optional]

The device object for the device that contains the file.


## -returns



None




## -remarks



The <b>FsRtlMdlReadCompleteDev</b> routine unlocks the pages in cache memory that the <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev~r6.md">FsRtlMdlReadDev</a> routine allocated.




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev~r6.md">FsRtlMdlReadDev</a>



 

 

