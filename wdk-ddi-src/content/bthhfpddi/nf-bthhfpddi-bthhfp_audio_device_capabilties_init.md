---
UID : NF:bthhfpddi.BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT
title : BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT function
author : windows-driver-content
description : The BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT method returns a pointer to an initialized BTHHFP_AUDIO_DEVICE_CAPABILTIES data structure.
old-location : audio\bthhfp_audio_device_capabilties_init.htm
old-project : audio
ms.assetid : c00b8f19-6708-4ec2-928b-610158850247
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT method [Audio Devices], audio.bthhfp_audio_device_capabilties_init, bthhfpddi/BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT, BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : bthhfpddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
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
req.irql : DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---


# BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT function
The 
			
            <b>BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT</b> method returns a pointer to an initialized <a href="https://msdn.microsoft.com/56c2bbb9-8fcd-43d4-9202-c8925575e44d">BTHHFP_AUDIO_DEVICE_CAPABILTIES</a> data structure.

## Syntax

````
FORCEINLINE VOID  BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT(
  _Out_ PBTHHFP_AUDIO_DEVICE_CAPABILTIES caps
);
````

## Parameters

`caps`

A pointer to an initialized <a href="https://msdn.microsoft.com/56c2bbb9-8fcd-43d4-9202-c8925575e44d">BTHHFP_AUDIO_DEVICE_CAPABILTIES</a> data structure.


## Return Value

This method does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | bthhfpddi.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | DISPATCH_LEVEL |