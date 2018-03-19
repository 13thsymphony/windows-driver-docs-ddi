---
UID: NN:wdtf.ITracer
title: ITracer
author: windows-driver-content
description: The ITracer interface enables individual instances of every WDTF interface to determine the specific tracing settings for a given implementation coclass. These settings are recorded in the registry.
old-location: dtf\itracer.htm
old-project: dtf
ms.assetid: 3873ed15-cb68-4442-8b4d-e4b370d29728
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ITracer, ITracer interface [Windows Device Testing Framework], ITracer interface [Windows Device Testing Framework], described, ITracer_dcaa8d23-ed67-4084-b214-0e2506076e77.xml, dtf.itracer, wdtf/ITracer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
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
req.type-library: WDTF.tlb
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTF.tlb
api_name:
-	ITracer
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# ITracer interface

The <b>ITracer</b> interface enables individual instances of every WDTF interface to determine the specific tracing settings for a given implementation coclass. These settings are recorded in the registry.

## Methods

<p>The <b>ITracer</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [ITracer::GetBits](nf-wdtf-itracer-getbits.md) | The GetBits method returns the set of tracing flags for a coclass as a bit mask, given a specified TTraceLevel value and the CLSID of the coclass. |

## Remarks
You will typically never see the <b>ITracer</b> interface. In fact, even if you are building WDTF action plug-ins, you will probably not need to use this interface. <b>ITracer</b> is implemented in WDTF.dll and provides the global definitions for the specific settings that are associated with each <a href="..\wdtf\ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md">TTraceLevel </a> enumeration value.

The following table describes the internal flags for WDTF tracing. The individual levels within the <a href="..\wdtf\ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md">TTraceLevel</a> enumeration correspond to a set of internal tracing flags. The registry key that is listed in TraceLevel Path (in the following Implementation Details section) contains the bit masks for each TTraceLevel, as the following table shows.

Trace2_Medium contains all of the Trace1_Low flags, and Trace3_High contains all of the Trace2_Medium flags.

<table>
<tr>
<th>Trace flag</th>
<th>Meaning</th>
<th>Bit</th>
<th>Default trace level</th>
</tr>
<tr>
<td>
COMEntryExit

</td>
<td>
A COM method or property for entry and exit

</td>
<td>
0x0001

</td>
<td>
Trace1_Low

</td>
</tr>
<tr>
<td>
COMError

</td>
<td>
An error was found by a COM method or property

</td>
<td>
0x0002

</td>
<td>
Trace1_Low

</td>
</tr>
<tr>
<td>
EntryExit

</td>
<td>
A C++ function for entry and exit

</td>
<td>
0x0004

</td>
<td>
Trace2_Medium

</td>
</tr>
<tr>
<td>
APICall

</td>
<td>
About to call into an API

</td>
<td>
0x0008

</td>
<td>
Trace2_Medium

</td>
</tr>
<tr>
<td>
Info

</td>
<td>
Extra information

</td>
<td>
0x0010

</td>
<td>
Trace2_Medium

</td>
</tr>
<tr>
<td>
Warning

</td>
<td>
Warning that something might be wrong

</td>
<td>
0x0020

</td>
<td>
Trace1_Low

</td>
</tr>
<tr>
<td>
Error

</td>
<td>
An error was found within WDTF

</td>
<td>
0x0040

</td>
<td>
Trace1_Low

</td>
</tr>
<tr>
<td>
NoisyCOMEntryExit

</td>
<td>
The noisy version of the COMError flag

</td>
<td>
0x0080

</td>
<td>
Trace3_High

</td>
</tr>
<tr>
<td>
NoisyEntryExit

</td>
<td>
The noisy version of the EntryExit flag

</td>
<td>
0x0100

</td>
<td>
Trace3_High

</td>
</tr>
<tr>
<td>
NoisyAPICall

</td>
<td>
The noisy version of the APICall flag

</td>
<td>
0x0200

</td>
<td>
Trace3_High

</td>
</tr>
<tr>
<td>
NoisyInfo

</td>
<td>
The noisy version of the Info flag

</td>
<td>
0x0400

</td>
<td>
Trace3_High

</td>
</tr>
<tr>
<td>
NoisyWarning

</td>
<td>
The noisy version of the Warning flag

</td>
<td>
0x0800

</td>
<td>
Trace3_High

</td>
</tr>
</table>
 

<b>Implementation Details</b>

ProgID: WDTF.Tracer

TraceLevel Path: HKCR\WDTF.Tracer.1\

<div class="alert"><b>Note</b>  The implementation of the <b>ITracer</b> interface is thread-safe.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wdtf.h |

## See Also

<a href="..\wdtf\ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md">TTraceLevel</a>



<a href="..\wdtf\nn-wdtf-itracing.md">ITracing</a>