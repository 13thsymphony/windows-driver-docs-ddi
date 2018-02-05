---
UID : NE:usb._USB_CONTROLLER_FLAVOR
title : "_USB_CONTROLLER_FLAVOR"
author : windows-driver-content
description : The USB_CONTROLLER_FLAVOR enumeration specifies the type of USB host controller.
old-location : buses\usb_controller_flavor.htm
old-project : usbref
ms.assetid : c732fe90-50fb-4f6e-b42e-cb35c1ed0091
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : OHCI_Generic, usb/UHCI_Intel, UHCI_VIA_x0E_FIFO, USB_HcGeneric, usb/UHCI_Ich6, usb/OHCI_Hydra, UHCI_Ich3m, UHCI_Ich1, usb/EHCI_NEC, usbstrct_a1b79c0b-7ee4-48bd-9793-8f37b9d248f2.xml, usb/UHCI_VIA_x02, UHCI_Ich2, usb/EHCI_NVIDIA_Tegra2, usb/UHCI_VIA_x03, usb/UHCI_Generic, usb/UHCI_VIA, UHCI_VIA_x04, usb/EHCI_Lucent, UHCI_Intel, usb/UHCI_Piix4, usb/UHCI_Ich1, UHCI_VIA_x03, usb/USB_CONTROLLER_FLAVOR, EHCI_Intel_Medfield, USB_CONTROLLER_FLAVOR enumeration [Buses], UHCI_Piix4, usb/UHCI_Ich2, usb/UHCI_Ich5, usb/UHCI_VIA_x01, _USB_CONTROLLER_FLAVOR, buses.usb_controller_flavor, OHCI_Hydra, OHCI_NEC, EHCI_Lucent, USB_CONTROLLER_FLAVOR, usb/OHCI_NEC, UHCI_VIA_x02, EHCI_NVIDIA_Tegra2, UHCI_Ich4, UHCI_Ich6, usb/USB_HcGeneric, usb/UHCI_VIA_x0E_FIFO, UHCI_Piix3, usb/UHCI_Ich4, UHCI_Generic, EHCI_Generic, usb/EHCI_Generic, usb/UHCI_Piix3, usb/UHCI_Ich3m, EHCI_NEC, usb/EHCI_Intel_Medfield, usb/OHCI_Generic, usb/EHCI_NVIDIA_Tegra3, UHCI_VIA, EHCI_NVIDIA_Tegra3, usb/UHCI_VIA_x04, UHCI_VIA_x01, UHCI_Ich5
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : usb.h
req.include-header : Usb.h
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
req.typenames : USB_CONTROLLER_FLAVOR
req.product : Windows 10 or later.
---

# _USB_CONTROLLER_FLAVOR Enumeration
The <b>USB_CONTROLLER_FLAVOR</b> enumeration specifies the type of USB host controller.

## Syntax
````
typedef enum _USB_CONTROLLER_FLAVOR { 
  USB_HcGeneric        = 0,
  OHCI_Generic         = 100,
  OHCI_Hydra           = 101,
  OHCI_NEC             = 102,
  UHCI_Generic         = 200,
  UHCI_Piix4           = 201,
  UHCI_Piix3           = 202,
  UHCI_Ich2            = 203,
  UHCI_Ich1            = 205,
  UHCI_Ich3m           = 206,
  UHCI_Ich4            = 207,
  UHCI_Ich5            = 208,
  UHCI_Ich6            = 209,
  UHCI_Intel           = 249,
  UHCI_VIA             = 250,
  UHCI_VIA_x01         = 251,
  UHCI_VIA_x02         = 252,
  UHCI_VIA_x03         = 253,
  UHCI_VIA_x04         = 254,
  UHCI_VIA_x0E_FIFO    = 264,
  EHCI_Generic         = 1000,
  EHCI_NEC             = 2000,
  EHCI_Lucent          = 3000,
  EHCI_NVIDIA_Tegra2   = 4000,
  EHCI_NVIDIA_Tegra3   = 4001,
  EHCI_Intel_Medfield  = 5001
} USB_CONTROLLER_FLAVOR;
````

## Constants

<table>

<tr>
<td>EHCI_Generic</td>
<td>Indicates a generic EHCI host controller.</td>
</tr>

<tr>
<td>EHCI_Intel_Medfield</td>
<td>Indicates an Intel Medfield host controller.</td>
</tr>

<tr>
<td>EHCI_Lucent</td>
<td>Indicates an EHCI Lucent host controller.</td>
</tr>

<tr>
<td>EHCI_NEC</td>
<td>Indicates an NEC EHCI host controller.</td>
</tr>

<tr>
<td>EHCI_NVIDIA_Tegra2</td>
<td>Indicates a Revision 2 NVIDIA Tegra EHCI host controller.</td>
</tr>

<tr>
<td>EHCI_NVIDIA_Tegra3</td>
<td>Indicates a Revision 3 NVIDIA Tegra EHCI host controller.</td>
</tr>

<tr>
<td>OHCI_Generic</td>
<td>Indicates a generic OHCI host controller.</td>
</tr>

<tr>
<td>OHCI_Hydra</td>
<td>Indicates a Hydra host controller.</td>
</tr>

<tr>
<td>OHCI_NEC</td>
<td>Indicates a NEC host controller.</td>
</tr>

<tr>
<td>UHCI_Generic</td>
<td>Indicates a generic UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_Ich1</td>
<td>Indicates an Intel 815 ICH1 UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_Ich2</td>
<td>Indicates an Intel ICH2 UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_Ich3m</td>
<td>Indicates an Intel ICH3m UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_Ich4</td>
<td>Indicates an Intel ICH4m UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_Ich5</td>
<td>Indicates an Intel ICH5m UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_Ich6</td>
<td>Indicates an Intel ICH6m UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_Intel</td>
<td>Indicates a generic Intel UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_Piix3</td>
<td>Indicates an Intel PIIX3 UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_Piix4</td>
<td>Indicates an Intel PIIX4 UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_Reserved204</td>
<td></td>
</tr>

<tr>
<td>UHCI_VIA</td>
<td>Indicates a generic VIA UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_VIA_x01</td>
<td>Indicates a Revision 1 VIA UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_VIA_x02</td>
<td>Indicates a Revision 2 VIA UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_VIA_x03</td>
<td>Indicates a Revision 3 VIA UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_VIA_x04</td>
<td>Indicates a Revision 4 VIA UHCI host controller.</td>
</tr>

<tr>
<td>UHCI_VIA_x0E_FIFO</td>
<td>Indicates a FIFO Revision VIA UHCI host controller.</td>
</tr>

<tr>
<td>USB_HcGeneric</td>
<td>Indicates a generic host controller.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usb.h (include Usb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539256">USB_CONTROLLER_INFO_0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_CONTROLLER_FLAVOR enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>