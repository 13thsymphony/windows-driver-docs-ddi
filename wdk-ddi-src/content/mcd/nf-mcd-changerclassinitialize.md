---
UID: NF:mcd.ChangerClassInitialize
title: ChangerClassInitialize function
author: windows-driver-content
description: The ChangerClassInitialize routine initializes the driver.
old-location: storage\changerclassinitialize.htm
old-project: storage
ms.assetid: b19f85f7-fe51-4539-8c36-e3c6a299faad
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ChangerClassInitialize, ChangerClassInitialize routine [Storage Devices], chgrclas_f0aa8547-be16-44aa-bd15-a4828d7f57f5.xml, mcd/ChangerClassInitialize, storage.changerclassinitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
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
req.lib: Mcd.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Mcd.lib
-	Mcd.dll
api_name:
-	ChangerClassInitialize
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---


# ChangerClassInitialize function
The <b>ChangerClassInitialize</b> routine initializes the driver.

## Syntax

````
NTSTATUS ChangerClassInitialize(
  _In_ PDRIVER_OBJECT  DriverObject,
  _In_ PUNICODE_STRING RegistryPath,
  _In_ PMCD_INIT_DATA  MCDInitData
);
````

## Parameters

`DriverObject`

Pointer to the changer miniclass driver object.  This is passed as a parameter to the miniclass driver's <b>DriverEntry</b> routine. The format of this object is operating system-specific and should not be interpreted by the miniclass driver.

`RegistryPath`

Pointer to the registry path for changer miniclass driver. This is also passed as a parameter to the miniclass driver's <b>DriverEntry</b> routine. The format of this is operating system-specific and should not be interpreted by the miniclass driver.

`ChangerInitData`

TBD


## Return Value

<b>ChangerClassInitialize</b> returns a value indicating the success or failure of  the driver initialization. If initialization is successful, <b>ChangerClassInitialize</b> returns STATUS_SUCCESS. Otherwise, <b>ChangerClassInitialize</b> returns an appropriate error message. Minidrivers should <i>not</i> interpret this error value, but should just return this value from their <b>DriverEntry</b> routine.

## Remarks

<b>ChangerClassInitialize</b> is a changer class driver routine that miniclass drivers can call in Microsoft Windows XP and later operating systems.

Changer miniclass drivers call <b>ChangerClassInitialize</b> from within their <b>DriverEntry</b> routines to initialize the driver. <b>ChangerClassInitialize</b> performs many tasks formerly performed by the changer class driver's <b>DriverEntry</b> routine such as registering the miniclass driver's dispatch routines. It allocates a driver object extension and copies the data contained in <i>MCDInitData</i> into the driver object extension along with other initialization data such as the driver's registry path and pointers to certain changer class driver routines that are operating system-specific. 

Changer miniclass drivers must allocate an <a href="..\mcd\ns-mcd-_mcd_init_data.md">MCD_INIT_DATA</a> structure, zero the structure by calling <a href="..\wdm\nf-wdm-rtlzeromemory.md">RtlZeroMemory</a>, and then assign values to the appropriate members, before passing the structure's address to <b>ChangerClassInitialize</b> by means of the <i>MCDInitData</i> parameter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mcd.h (include Mcd.h, Ntddchgr.h) |
| **Library** | Mcd.lib |

## See Also

<a href="..\mcd\ns-mcd-_mcd_init_data.md">MCD_INIT_DATA</a>



<a href="..\wdm\nf-wdm-rtlzeromemory.md">RtlZeroMemory</a>