---
UID : NS:wdm._EXT_DELETE_PARAMETERS
title : "_EXT_DELETE_PARAMETERS"
author : windows-driver-content
description : The EXT_DELETE_PARAMETERS structure contains an extended set of parameters for the ExDeleteTimer routine.
old-location : kernel\ext_delete_parameters.htm
old-project : kernel
ms.assetid : B2EADC0E-837A-4231-8794-43933DAA69E7
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PEXT_DELETE_PARAMETERS, wdm/EXT_DELETE_PARAMETERS, *PEXT_DELETE_PARAMETERS, wdm/PEXT_DELETE_PARAMETERS, _EXT_DELETE_PARAMETERS, EXT_DELETE_PARAMETERS, kernel.ext_delete_parameters, EXT_DELETE_PARAMETERS structure [Kernel-Mode Driver Architecture], PEXT_DELETE_PARAMETERS structure pointer [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 8.1.
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
req.typenames : "*PEXT_DELETE_PARAMETERS, EXT_DELETE_PARAMETERS"
req.product : Windows 10 or later.
---

# _EXT_DELETE_PARAMETERS structure
The <b>EXT_DELETE_PARAMETERS</b> structure contains an extended set of parameters for the <a href="..\wdm\nf-wdm-exdeletetimer.md">ExDeleteTimer</a> routine.

## Syntax
````
typedef struct _EXT_DELETE_PARAMETERS {
  ULONG                Version;
  ULONG                Reserved;
  PEXT_DELETE_CALLBACK DeleteCallback;
  PVOID                DeleteContext;
} EXT_DELETE_PARAMETERS, *PEXT_DELETE_PARAMETERS;
````

## Members


`DeleteCallback`

A pointer to a driver-implemented <a href="https://msdn.microsoft.com/library/windows/hardware/dn265192">ExTimerDeleteCallback</a> callback routine. The operating system calls this routine when the timer is deleted. This parameter is optional and can be <b>NULL</b> if no timer-deletion callback routine is needed.

The <b>ExInitializeDeleteTimerParameters</b> routine sets this member to <b>NULL</b>. For more information, see Remarks.

`DeleteContext`

A context value for the timer-deletion callback routine. The operating system passes this value as a parameter to the timer-deletion callback routine, if one is specified. This parameter is typically a pointer to a caller-defined structure that contains context information used by the callback routine. This parameter is optional and can be set to <b>NULL</b> if no context information is needed. 

The <b>ExInitializeDeleteTimerParameters</b> routine sets this member to <b>NULL</b>.

`Reserved`

Set to zero. The <b>ExInitializeDeleteTimerParameters</b> routine sets this member to zero.

`Version`

The version number of this <b>EXT_DELETE_PARAMETERS</b> structure. The <a href="..\wdm\nf-wdm-exinitializedeletetimerparameters.md">ExInitializeDeleteTimerParameters</a> routine sets this member to the correct version number.

## Remarks
The <i>Parameters</i> parameter of the <a href="..\wdm\nf-wdm-exdeletetimer.md">ExDeleteTimer</a> routine is a pointer to an <b>EXT_DELETE_PARAMETERS</b> structure. Before passing an <b>EXT_DELETE_PARAMETERS</b> structure to this routine, call the <a href="..\wdm\nf-wdm-exinitializedeletetimerparameters.md">ExInitializeDeleteTimerParameters</a> routine to initialize the structure.

Your driver can use an <a href="https://msdn.microsoft.com/library/windows/hardware/dn265192">ExTimerDeleteCallback</a> callback routine to free any storage or other system resources that the driver might have previously allocated to use with the timer object that is being deleted. For example, the driver's context value might point to a caller-allocated structure that needs to be freed if the timer object is to be deleted. The operating system calls the <i>ExTimerDeleteCallback</i> routine only after the timer object has been disabled to prevent further timer operations and any pending timer operation on the timer object is canceled or completed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265192">ExTimerDeleteCallback</a>

<a href="..\wdm\nf-wdm-exinitializedeletetimerparameters.md">ExInitializeDeleteTimerParameters</a>

<a href="..\wdm\nf-wdm-exdeletetimer.md">ExDeleteTimer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20EXT_DELETE_PARAMETERS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>