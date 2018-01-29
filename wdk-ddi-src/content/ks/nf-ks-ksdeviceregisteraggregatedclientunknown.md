---
UID : NF:ks.KsDeviceRegisterAggregatedClientUnknown
title : KsDeviceRegisterAggregatedClientUnknown function
author : windows-driver-content
description : This inline function is a wrapper for KsRegisterAggregatedClientUnknown.
old-location : stream\ksdeviceregisteraggregatedclientunknown.htm
old-project : stream
ms.assetid : d4d3f653-cfdc-4567-97bc-def26484ed9f
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.ksdeviceregisteraggregatedclientunknown, KsDeviceRegisterAggregatedClientUnknown function [Streaming Media Devices], KsDeviceRegisterAggregatedClientUnknown, ks/KsDeviceRegisterAggregatedClientUnknown, avfunc_3e7aa517-80e8-498c-939d-1769393479fb.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---


# KsDeviceRegisterAggregatedClientUnknown function
This inline function is a wrapper for <a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>.

## Syntax

````
PUNKNOWN __inline KsDeviceRegisterAggregatedClientUnknown(
  _In_ PKSDEVICE Device,
  _In_ PUNKNOWN  ClientUnknown
);
````

## Parameters

`Device`

A pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure representing the specified AVStream device.

`ClientUnknown`

A pointer to the client's undelegated <b>IUnknown</b> interface.


## Return Value

Returns the newly created aggregate object.

## Remarks

This inline function performs a typecast and then calls <a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDeviceRegisterAggregatedClientUnknown function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>