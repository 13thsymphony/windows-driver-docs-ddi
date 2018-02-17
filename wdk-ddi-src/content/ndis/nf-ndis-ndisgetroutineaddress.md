---
UID: NF:ndis.NdisGetRoutineAddress
title: NdisGetRoutineAddress function
author: windows-driver-content
description: The NdisGetRoutineAddress function returns the address of a routine given the routine's name.
old-location: netvista\ndisgetroutineaddress.htm
old-project: netvista
ms.assetid: 98257b56-e586-41e7-80c3-f9f96d471125
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisGetRoutineAddress, netvista.ndisgetroutineaddress, NdisGetRoutineAddress, ndis_sysinfo_ref_d2259157-f4fd-4fd8-b86e-f685ab4213d5.xml, NdisGetRoutineAddress function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetRoutineAddress (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetRoutineAddress (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisGetRoutineAddress
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisGetRoutineAddress function
The 
  <b>NdisGetRoutineAddress</b> function returns the address of a routine given the routine's name.

## Syntax

````
PVOID NdisGetRoutineAddress(
  _In_ PNDIS_STRING NdisRoutineName
);
````

## Parameters

`NdisRoutineName`

A pointer to a 
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that specifies the
     string that contains the name of a routine.


## Return Value

Returns the address of the routine whose name is specified at 
     <i>NdisRoutineName</i> if the routine is available; otherwise, <b>NULL</b>.

## Remarks

An NDIS driver can use 
    <b>NdisGetRoutineAddress</b> to obtain the address of an exported NDIS routine. The driver can then use
    this address to call the NDIS routine.

An NDIS driver can use 
    <b>NdisGetRoutineAddress</b> if the driver must remain backward compatible. For example, if such a driver
    imports an NDIS routine that is not exported by the version of NDIS that is currently running, the I/O
    manager will not load the driver on the operating system. However, the driver can first use 
    <b>NdisGetRoutineAddress</b> to determine whether the routine is available in the version of NDIS that is
    currently running. If available, the address of the routine is returned. The driver can then use the
    address to call the routine. If not available, <b>NULL</b> is returned. The driver cannot call the routine, but
    the driver still loads on the operating system.

No performance improvement is gained by using the address that is returned by 
    <b>NdisGetRoutineAddress</b> instead of calling the specified routine by name. Therefore, do not write an
    NDIS driver to use 
    <b>NdisGetRoutineAddress</b> if you know that the NDIS version with which the driver will run exports the
    specified routine.

Typically, an NDIS driver calls 
    <b>NdisGetRoutineAddress</b> in its 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetRoutineAddress (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetRoutineAddress (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetRoutineAddress function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>