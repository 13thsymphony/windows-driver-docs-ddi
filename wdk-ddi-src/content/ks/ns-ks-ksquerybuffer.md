---
UID : NS:ks.KSQUERYBUFFER
title : KSQUERYBUFFER
author : windows-driver-content
description : The KSQUERYBUFFER structure is used when querying for outstanding buffers available on an event with KSEVENT_TYPE_QUERYBUFFER.
old-location : stream\ksquerybuffer.htm
old-project : stream
ms.assetid : 6827df53-f970-4ceb-961d-b4b95fa56cfe
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSQUERYBUFFER, ks/KSQUERYBUFFER, stream.ksquerybuffer, ks/PKSQUERYBUFFER, PKSQUERYBUFFER structure pointer [Streaming Media Devices], PKSQUERYBUFFER, *PKSQUERYBUFFER, ks-struct_aa45ed01-603d-4452-8862-649a73361c48.xml, KSQUERYBUFFER structure [Streaming Media Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
req.target-type : Windows
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : KSQUERYBUFFER, *PKSQUERYBUFFER
---

# KSQUERYBUFFER structure
The KSQUERYBUFFER structure is used when querying for outstanding buffers available on an event with KSEVENT_TYPE_QUERYBUFFER<b>.</b>

## Syntax
````
typedef struct {
  KSEVENT      Event;
  PKSEVENTDATA EventData;
  PVOID        Reserved;
} KSQUERYBUFFER, *PKSQUERYBUFFER;
````

## Members


`Event`

Specifies the description of the original event, with the KSEVENT_TYPE_QUERYBUFFER flag set instead of the KSEVENT_TYPE_ENABLEBUFFERED flag.

`EventData`

A pointer to a <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure. This is the same pointer supplied to <a href="..\ks\nc-ks-pfnksaddevent.md">AVStrMiniAddEvent</a> at event enable time. This pointer is used as the unique identifier in locating the event, just as it is used when disabling the event.

`Reserved`

Not used, and set to zero.

## Remarks
If KSEVENT_TYPE_ENABLEBUFFERED was used to enable an event that also buffers data, then the data produced by the event can be queried using this method. The description of the event being queried is provided as the first parameter, and any buffer is provided as the second parameter to the query.

The buffer length needed can be queried by providing a zero length output buffer. The size of buffer is returned in the <b>BytesReturned</b> parameter, with a warning status of STATUS_BUFFER_OVERFLOW.

Alternatively, the query returns one of the following status values:
<table>
<tr>
<th>Return Value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_NOT_FOUND

</td>
<td>
event was not found

</td>
</tr>
<tr>
<td>
STATUS_INVALID_PARAMETER

</td>
<td>
it was not being buffered

</td>
</tr>
<tr>
<td>
STATUS_NO_MORE_ENTRIES

</td>
<td>
no buffers were available

</td>
</tr>
<tr>
<td>
STATUS_BUFFER_TOO_SMALL

</td>
<td>
buffer size was insufficient.

</td>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
life is good.

</td>
</tr>
</table>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a>

<a href="..\ks\ns-ks-ksbuffer_item.md">KSBUFFER_ITEM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSQUERYBUFFER structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>