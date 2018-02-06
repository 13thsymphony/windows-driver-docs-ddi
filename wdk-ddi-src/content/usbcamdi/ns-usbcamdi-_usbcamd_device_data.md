---
UID: NS:usbcamdi._USBCAMD_DEVICE_DATA
title: "_USBCAMD_DEVICE_DATA"
author: windows-driver-content
description: This structure is obsolete and is provided to maintain backward compatibility with the original USBCAMD.
old-location: stream\usbcamd_device_data.htm
old-project: stream
ms.assetid: 1841be02-e30f-4685-82ea-2d9c02ce7277
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: usbcamdi/PUSBCAMD_DEVICE_DATA, USBCAMD_DEVICE_DATA structure [Streaming Media Devices], _USBCAMD_DEVICE_DATA, USBCAMD_DEVICE_DATA, usbcamdi/USBCAMD_DEVICE_DATA, PUSBCAMD_DEVICE_DATA structure pointer [Streaming Media Devices], PUSBCAMD_DEVICE_DATA, *PUSBCAMD_DEVICE_DATA, usbcmdpr_1e4ea0e1-71e0-4c0e-a2bd-668f8fac9b02.xml, stream.usbcamd_device_data
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbcamdi.h
apiname:
-	USBCAMD_DEVICE_DATA
product: Windows
targetos: Windows
req.typenames: "*PUSBCAMD_DEVICE_DATA, USBCAMD_DEVICE_DATA"
req.product: Windows 10 or later.
---

# _USBCAMD_DEVICE_DATA structure
This structure is <b>obsolete</b> and is provided to maintain backward compatibility with the original USBCAMD. New camera minidrivers should use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data2.md">USBCAMD_DEVICE_DATA2</a> structure.

The USBCAMD_DEVICE_DATA structure specifies the entry points for a camera minidriver's functions that the original USBCAMD calls.

## Syntax
````
typedef struct _USBCAMD_DEVICE_DATA {
  ULONG                          Sig;
  PCAM_INITIALIZE_ROUTINE        CamInitialize;
  PCAM_INITIALIZE_ROUTINE        CamUnInitialize;
  PCAM_PROCESS_PACKET_ROUTINE    CamProcessUSBPacket;
  PCAM_NEW_FRAME_ROUTINE         CamNewVideoFrame;
  PCAM_PROCESS_RAW_FRAME_ROUTINE CamProcessRawVideoFrame;
  PCAM_START_CAPTURE_ROUTINE     CamStartCapture;
  PCAM_STOP_CAPTURE_ROUTINE      CamStopCapture;
  PCAM_CONFIGURE_ROUTINE         CamConfigure;
  PCAM_STATE_ROUTINE             CamSaveState;
  PCAM_STATE_ROUTINE             CamRestoreState;
  PCAM_ALLOCATE_BW_ROUTINE       CamAllocateBandwidth;
  PCAM_FREE_BW_ROUTINE           CamFreeBandwidth;
} USBCAMD_DEVICE_DATA, *PUSBCAMD_DEVICE_DATA;
````

## Members


`CamAllocateBandwidth`

Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_allocate_bw_routine.md">CamAllocateBandwidth</a> callback function. This entry point is required.

`CamConfigure`

Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_configure_routine.md">CamConfigure</a> callback function. This entry point is required.

`CamFreeBandwidth`

Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_free_bw_routine.md">CamFreeBandwidth</a> callback function. This entry point is required.

`CamInitialize`

Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_initialize_routine.md">CamInitialize</a> callback function. This entry point is required.

`CamNewVideoFrame`

Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_new_frame_routine.md">CamNewVideoFrame</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

`CamProcessRawVideoFrame`

Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine.md">CamProcessRawVideoFrame</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

`CamProcessUSBPacket`

Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_process_packet_routine.md">CamProcessUSBPacket</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

`CamRestoreState`

Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_state_routine.md">CamRestoreState</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

`CamSaveState`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557635">CamSaveState</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

`CamStartCapture`

Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_start_capture_routine.md">CamStartCapture</a> callback function. This entry point is required.

`CamStopCapture`

Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_stop_capture_routine.md">CamStopCapture</a> callback function. This entry point is required.

`CamUnInitialize`

Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557646">CamUnInitialize</a> callback function. This entry point is required.

`Sig`

Reserved. Do not use.

## Remarks
A camera minidriver passes a USBCAMD_DEVICE_DATA structure to USBCAMD as a parameter to the USBCAMD library routine <a href="..\usbcamdi\nf-usbcamdi-usbcamd_adapterreceivepacket.md">USBCAMD_AdapterReceivePacket</a> in the original USBCAMD.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

## See Also

<a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data2.md">USBCAMD_DEVICE_DATA2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_DEVICE_DATA structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>