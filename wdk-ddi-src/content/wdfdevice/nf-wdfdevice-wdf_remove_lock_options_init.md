---
UID: NF:wdfdevice.WDF_REMOVE_LOCK_OPTIONS_INIT
title: WDF_REMOVE_LOCK_OPTIONS_INIT function
author: windows-driver-content
description: The WDF_REMOVE_LOCK_OPTIONS_INIT function initializes a WDF_REMOVE_LOCK_OPTIONS structure.
old-location: wdf\wdf_remove_lock_options_init.htm
old-project: wdf
ms.assetid: 08D0CE94-E37E-4BAE-99C8-FB4EDF7BCDDB
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WDF_REMOVE_LOCK_OPTIONS_INIT, WDF_REMOVE_LOCK_OPTIONS_INIT function, wdf.wdf_remove_lock_options_init, kmdf.wdf_remove_lock_options_init, wdfdevice/WDF_REMOVE_LOCK_OPTIONS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_REMOVE_LOCK_OPTIONS_INIT
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WDF_REMOVE_LOCK_OPTIONS_INIT function
<p class="CCE_Message">[Applies to KMDF only]


   The 
  <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b> function initializes a <a href="..\wdfdevice\ns-wdfdevice-_wdf_remove_lock_options.md">WDF_REMOVE_LOCK_OPTIONS</a> structure.

## Syntax

````
__inline
void WDF_REMOVE_LOCK_OPTIONS_INIT(
  _Out_ PWDF_REMOVE_LOCK_OPTIONS RemoveLockOptions,
  _In_  ULONG                    Flags
);
````

## Parameters

`RemoveLockOptions`

A pointer to a <a href="..\wdfdevice\ns-wdfdevice-_wdf_remove_lock_options.md">WDF_REMOVE_LOCK_OPTIONS</a> structure.

`Flags`

<a href="..\wdfdevice\ne-wdfdevice-_wdf_remove_lock_options_flags.md">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a>-typed flags.


## Return Value

This function does not return a value.

## Remarks

The <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b> function zeros the <a href="..\wdfdevice\ns-wdfdevice-_wdf_remove_lock_options.md">WDF_REMOVE_LOCK_OPTIONS</a> structure that the <i>RemoveLockOptions</i> parameter specifies and sets its <b>Size</b> member. This function also sets the structure's <b>Flags</b> member to the value provided in the <i>Flags</i> parameter.

Before a driver calls <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetremovelockoptions.md">WdfDeviceInitSetRemoveLockOptions</a>, it must call <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b> to initialize a <a href="..\wdfdevice\ns-wdfdevice-_wdf_remove_lock_options.md">WDF_REMOVE_LOCK_OPTIONS</a> structure.

For a code example that uses <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b>, see <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetremovelockoptions.md">WdfDeviceInitSetRemoveLockOptions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\wdfdevice\ne-wdfdevice-_wdf_remove_lock_options_flags.md">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a>



<a href="..\wdfdevice\ns-wdfdevice-_wdf_remove_lock_options.md">WDF_REMOVE_LOCK_OPTIONS</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetremovelockoptions.md">WdfDeviceInitSetRemoveLockOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REMOVE_LOCK_OPTIONS_INIT function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>