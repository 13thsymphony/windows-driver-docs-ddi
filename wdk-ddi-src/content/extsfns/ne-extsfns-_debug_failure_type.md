---
UID : NE:extsfns._DEBUG_FAILURE_TYPE
title : _DEBUG_FAILURE_TYPE
author : windows-driver-content
description : The values in the DEBUG_FAILURE_TYPE enumeration indicate the type of a failure.
old-location : debugger\debug_failure_type.htm
old-project : debugger
ms.assetid : BFCFE35A-5697-4F9D-B0A1-51EB5D8AE690
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _DEBUG_FAILURE_TYPE, DEBUG_FAILURE_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : extsfns.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DEBUG_FAILURE_TYPE
req.alt-loc : extsfns.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : DEBUG_FAILURE_TYPE
---

# _DEBUG_FAILURE_TYPE Enumeration
The values in the <b>DEBUG_FAILURE_TYPE</b> enumeration indicate the type of a failure.

## Syntax
````
typedef enum _DEBUG_FAILURE_TYPE { 
  DEBUG_FLR_UNKNOWN,
  DEBUG_FLR_KERNEL,
  DEBUG_FLR_USER_CRASH,
  DEBUG_FLR_IE_CRASH
} DEBUG_FAILURE_TYPE;
````

## Constants

<table>

<tr>
<td>DEBUG_FLR_IE_CRASH</td>
<td>The failure occurred in the application iexplore.exe.</td>
</tr>

<tr>
<td>DEBUG_FLR_KERNEL</td>
<td>The failing code was running in kernel mode.</td>
</tr>

<tr>
<td>DEBUG_FLR_UNKNOWN</td>
<td>The failure type is not known.</td>
</tr>

<tr>
<td>DEBUG_FLR_USER_CRASH</td>
<td>The failing code was running in user mode.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | extsfns.h |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>
</dt>
<dt>
<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_FAILURE_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>