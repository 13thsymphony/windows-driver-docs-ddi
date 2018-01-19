---
UID : NS:usb._USBD_STREAM_INFORMATION
title : _USBD_STREAM_INFORMATION
author : windows-driver-content
description : The USBD_STREAM_INFORMATION structure stores information about a stream associated with a bulk endpoint.
old-location : buses\usbd_stream_information.htm
old-project : usbref
ms.assetid : AFB502BF-4BC2-439E-BF1F-5D1DE3172362
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _USBD_STREAM_INFORMATION, *PUSBD_STREAM_INFORMATION, USBD_STREAM_INFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usb.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USBD_STREAM_INFORMATION
req.alt-loc : Usb.h
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
req.typenames : "*PUSBD_STREAM_INFORMATION, USBD_STREAM_INFORMATION"
req.product : Windows 10 or later.
---

# _USBD_STREAM_INFORMATION structure
The <b>USBD_STREAM_INFORMATION</b> structure stores information about a stream associated with a bulk endpoint.

## Syntax
````
typedef struct _USBD_STREAM_INFORMATION {
  USBD_PIPE_HANDLE PipeHandle;
  ULONG            StreamID;
  ULONG            MaximumTransferSize;
  ULONG            PipeFlags;
} USBD_STREAM_INFORMATION, *PUSBD_STREAM_INFORMATION;
````

## Members

        
            `MaximumTransferSize`

            Maximum transfer size (in bytes) that a client driver can send in a single URB for an I/O transfer to the stream.
        
            `PipeFlags`

            Reserved. Do not use.
        
            `PipeHandle`

            An opaque handle to  the stream.
        
            `StreamID`

            Stream identifier. The open-static streams request obtains stream identifiers that are assigned by the USB driver stack.

    ## Remarks
        A client driver allocates an array of  <b>USBD_STREAM_INFORMATION</b> structures and sends it in an open-streams request (URB_FUNCTION_OPEN_STATIC_STREAMS).  Upon completion, the USB driver stack retrieves stream information and populates each <b>USBD_STREAM_INFORMATION</b> structure with stream information.  The stream identifiers returned by the request are sequential and start at 1.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usb.h |

    ## See Also

        <dl>
<dt>
<a href="..\usb\ns-usb-_urb.md">URB</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_open_static_streams.md">_URB_OPEN_STATIC_STREAMS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_STREAM_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>