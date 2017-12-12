---
UID: NS.PRINTOEM._PSCRIPT5_PRIVATE_DEVMODE
title: _PSCRIPT5_PRIVATE_DEVMODE
author: windows-driver-content
description: The PSCRIPT5_PRIVATE_DEVMODE structure enables Pscript5 plug-ins to determine the size of the private portion of Pscript5's DEVMODEW structure.
old-location: print\pscript5_private_devmode.htm
old-project: print
ms.assetid: e2ae002b-2bc9-4e5e-b9b6-bb76849c2cba
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: _PSCRIPT5_PRIVATE_DEVMODE, PSCRIPT5_PRIVATE_DEVMODE, *PPSCRIPT5_PRIVATE_DEVMODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PSCRIPT5_PRIVATE_DEVMODE
req.alt-loc: printoem.h
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
req.product: Windows 10 or later.
---

# _PSCRIPT5_PRIVATE_DEVMODE structure



## -description
The PSCRIPT5_PRIVATE_DEVMODE structure enables Pscript5 plug-ins to determine the size of the private portion of Pscript5's DEVMODEW structure.



## -syntax

````
typedef struct _PSCRIPT5_PRIVATE_DEVMODE {
  WORD wReserved[57];
  WORD wSize;
} PSCRIPT5_PRIVATE_DEVMODE, *PPSCRIPT5_PRIVATE_DEVMODE;
````


## -struct-fields

### -field wReserved

Reserved for system use.


### -field wSize

The size, in bytes, of the private portion of Pscript5's <a href="display.devmodew">DEVMODEW</a> structure.


## -remarks
This structure and associated macro are available in Windows 2000 and later. For information about the public and private sections of the DEVMODEW structure, see <a href="https://msdn.microsoft.com/26212e3b-a591-4ed6-b441-b130d8d4d948">The DEVMODEW Structure</a>. 

Printoem.h defines a macro that you can use to determine the size of the private portion of Pscript5's DEVMODEW structure.

The <i>pdm</i> argument in the <b>GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE</b> macro is a pointer to a DEVMODEW structure. The macro determines whether the value of the <b>dmDriverExtra</b> member of the DEVMODEW structure is larger than the byte offset of the <b>wSize</b> member of the PSCRIPT5_PRIVATE_DEVMODE structure. If so, the macro returns the value of the <b>wSize</b> member in the PSCRIPT5_PRIVATE_DEVMODE structure. If not, the macro returns zero.

To safely determine the address of the private portion of your plug-in's DEVMODEW structure, do the following:

Call the <b>GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE</b> macro, passing the address of the DEVMODEW structure in the call.

Verify that (pdm)-&gt;dmDriverExtra is larger than the value returned by the macro. (The macro returns the value of the <b>wSize</b> member of the PSCRIPT5_PRIVATE_DEVMODE structure.)

The preceding example starts with the address of the public DEVMODEW structure (<i>pdm</i>), adds the number of bytes of this structure (<i>pdm-</i>&gt;<b>dmSize</b>), and then adds the size in bytes of the Pscript5 private DEVMODEW structure (<b>wSize</b>). A plug-in's private DEVMODEW data begins at this memory address. If there are multiple plug-ins chained together, the address returned by this example is that of the first plug-in's private DEVMODEW data. The second plug-in's private DEVMODEW data follows the first plug-in's private DEVMODEW data, the third plug-in's private DEVMODEW data follows that of the second plug-in's private DEVMODEW data, and so on. A plug-in developer who needs to determine the address of the <i>n</i>-th plug-in's private DEVMODEW data must know the sizes of the private DEVMODEW data for the first <i>n</i> - 1 plug-ins.

Verify that the private portion of your plug-in's DEVMODEW structure begins with a valid <a href="print.oem_dmextraheader">OEM_DMEXTRAHEADER</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Printoem.h (include Printoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.unidrv_private_devmode">UNIDRV_PRIVATE_DEVMODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PSCRIPT5_PRIVATE_DEVMODE structure%20 RELEASE:%20(12/9/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

