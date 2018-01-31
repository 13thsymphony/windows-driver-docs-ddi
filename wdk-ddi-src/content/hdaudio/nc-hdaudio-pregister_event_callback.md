---
UID : NC:hdaudio.PREGISTER_EVENT_CALLBACK
title : PREGISTER_EVENT_CALLBACK
author : windows-driver-content
description : The RegisterEventCallback routine registers a callback routine for an unsolicited response from a codec or codecs.The function pointer type for a RegisterEventCallback routine is defined as:
old-location : audio\registereventcallback.htm
old-project : audio
ms.assetid : 0f94146b-aa60-4106-aba6-0f1cb3e53008
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audio.registereventcallback, RegisterEventCallback callback function [Audio Devices], RegisterEventCallback, PREGISTER_EVENT_CALLBACK, PREGISTER_EVENT_CALLBACK, hdaudio/RegisterEventCallback, aud-prop2_4ef71e0f-0887-4d20-8198-cb5b9c161647.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : hdaudio.h
req.include-header : Hdaudio.h
req.target-type : Desktop
req.target-min-winverclnt : 
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
req.irql : PASSIVE_LEVEL (See Remarks section)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT"
---


# PREGISTER_EVENT_CALLBACK callback function
The <i>RegisterEventCallback</i> routine registers a callback routine for an unsolicited response from a codec or codecs.

The function pointer type for a <i>RegisterEventCallback</i> routine is defined as:

## Syntax

```
PREGISTER_EVENT_CALLBACK PregisterEventCallback;

NTSTATUS PregisterEventCallback(
  PVOID _context,
  PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK Routine,
  PVOID Context,
  PUCHAR Tag
)
{...}
```

## Parameters

`_context`



`Routine`



`Context`



`Tag`




## Return Value

<i>RegisterEventCallback</i> returns STATUS_SUCCESS if the call succeeds in registering the event. Otherwise, the routine returns an appropriate error code. The following table shows a possible return status code.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that not enough resources are available to complete the operation.

</td>
</tr>
</table>

## Remarks

This routine registers a callback routine for an unsolicited response from a codec. The routine outputs a tag to identify the unsolicited response. When the HD Audio bus driver encounters an unsolicited response from any codec with a matching tag value, the routine calls the specified callback routine at IRQL DISPATCH_LEVEL and passes the specified context value to the routine as a call parameter.

Following the call to <i>RegisterEventCallback</i>, the function driver is responsible for programming the codec or codecs to generate unsolicited responses with the specified tag.

The routine assigns a unique tag to each registered callback routine. The unique association between tag and callback routine persists as long as the callback routine remains registered. The function driver can delete the registration of a callback routine by calling <a href="..\hdaudio\nc-hdaudio-punregister_event_callback.md">UnregisterEventCallback</a>.

Currently, the bus driver can supply up to 64 unique tags per codec.

The callback parameter is a function pointer to a callback routine in the function driver. The function pointer type for the callback routine is defined as:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
  (*PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK)
    (HDAUDIO_CODEC_RESPONSE, PVOID);</pre>
</td>
</tr>
</table></span></div>The first call parameter is a structure of type <a href="..\hdaudio\ns-hdaudio-_hdaudio_codec_response.md">HDAUDIO_CODEC_RESPONSE</a> that specifies the codec's response to the command. This structure is passed by value. The second call parameter is the <i>callbackContext</i> value that was passed previously to <i>RegisterEventCallback</i>. The HD Audio bus driver calls the callback routine at IRQL DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hdaudio.h (include Hdaudio.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL (See Remarks section) |
| **DDI compliance rules** |  |

## See Also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>

<a href="..\hdaudio\ns-hdaudio-_hdaudio_codec_response.md">HDAUDIO_CODEC_RESPONSE</a>

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>

<a href="..\hdaudio\nc-hdaudio-punregister_event_callback.md">UnregisterEventCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PREGISTER_EVENT_CALLBACK callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>