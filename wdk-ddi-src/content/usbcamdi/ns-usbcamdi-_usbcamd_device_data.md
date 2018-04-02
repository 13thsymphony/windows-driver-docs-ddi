---
UID: NS:usbcamdi._USBCAMD_DEVICE_DATA
title: "_USBCAMD_DEVICE_DATA"
author: windows-driver-content
description: This structure is obsolete and is provided to maintain backward compatibility with the original USBCAMD.
old-location: stream\usbcamd_device_data.htm
old-project: stream
ms.assetid: 1841be02-e30f-4685-82ea-2d9c02ce7277
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PUSBCAMD_DEVICE_DATA, PUSBCAMD_DEVICE_DATA, PUSBCAMD_DEVICE_DATA structure pointer [Streaming Media Devices], USBCAMD_DEVICE_DATA, USBCAMD_DEVICE_DATA structure [Streaming Media Devices], _USBCAMD_DEVICE_DATA, stream.usbcamd_device_data, usbcamdi/PUSBCAMD_DEVICE_DATA, usbcamdi/USBCAMD_DEVICE_DATA, usbcmdpr_1e4ea0e1-71e0-4c0e-a2bd-668f8fac9b02.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
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
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbcamdi.h
api_name:
-	USBCAMD_DEVICE_DATA
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA, *PUSBCAMD_DEVICE_DATA
req.product: Windows 10 or later.
---

# _USBCAMD_DEVICE_DATA structure
This structure is <b>obsolete</b> and is provided to maintain backward compatibility with the original USBCAMD. New camera minidrivers should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568590">USBCAMD_DEVICE_DATA2</a> structure.

The USBCAMD_DEVICE_DATA structure specifies the entry points for a camera minidriver's functions that the original USBCAMD calls.

## Syntax
```
typedef struct _USBCAMD_DEVICE_DATA {
  ULONG                          Sig;
  PCAM_INITIALIZE_ROUTINE        CamInitialize;
  PCAM_INITIALIZE_ROUTINE        CamUnInitialize;
  PCAM_PROCESS_PACKET_ROUTINE    CamProcessUSBPacket;
  PCAM_NEW_FRAME_ROUTINE         CamNewVideoFrame;
  PCAM_PROCESS_RAW_FRAME_ROUTINE CamProcessRawVideoFrame;
  PCAM_START_CAPTURE_ROUTINE     CamStartCapture;
  PCAM_STOP_CAPTURE_ROUTINE      CamStopCapture;
  PCAM_CONFIGURE_ROUTINE         CamConfigure;
  PCAM_STATE_ROUTINE             CamSaveState;
  PCAM_STATE_ROUTINE             CamRestoreState;
  PCAM_ALLOCATE_BW_ROUTINE       CamAllocateBandwidth;
  PCAM_FREE_BW_ROUTINE           CamFreeBandwidth;
} USBCAMD_DEVICE_DATA, *PUSBCAMD_DEVICE_DATA;
```

## Members


`Sig`

Reserved. Do not use.

`CamInitialize`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557614">CamInitialize</a> callback function. This entry point is required.

`CamUnInitialize`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557646">CamUnInitialize</a> callback function. This entry point is required.

`CamProcessUSBPacket`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557629">CamProcessUSBPacket</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

`CamNewVideoFrame`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557617">CamNewVideoFrame</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

`CamProcessRawVideoFrame`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557623">CamProcessRawVideoFrame</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

`CamStartCapture`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557637">CamStartCapture</a> callback function. This entry point is required.

`CamStopCapture`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557642">CamStopCapture</a> callback function. This entry point is required.

`CamConfigure`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557603">CamConfigure</a> callback function. This entry point is required.

`CamSaveState`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557635">CamSaveState</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

`CamRestoreState`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557633">CamRestoreState</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

`CamAllocateBandwidth`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557595">CamAllocateBandwidth</a> callback function. This entry point is required.

`CamFreeBandwidth`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557611">CamFreeBandwidth</a> callback function. This entry point is required.

## Remarks
A camera minidriver passes a USBCAMD_DEVICE_DATA structure to USBCAMD as a parameter to the USBCAMD library routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff568574">USBCAMD_AdapterReceivePacket</a> in the original USBCAMD.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568590">USBCAMD_DEVICE_DATA2</a>