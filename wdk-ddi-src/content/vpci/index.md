---
UID: NA:
---

# Vpci.h header

## -description

This header is used by Windows kernel. For more information, see
- [Windows kernel](../_kernel/index.md)

Vpci.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [VPCI_READ_BLOCK callback](nc-vpci-vpci_read_block.md) | The ReadVfConfigBlock routine reads a block of configuration data for a PCI Express (PCIe) virtual function (VF). This routine is called by the driver of a PCIe VF on a device that supports the single root I/O virtualization (SR-IOV) interface. |
| [VPCI_WRITE_BLOCK callback](nc-vpci-vpci_write_block.md) | The WriteVfConfigBlock routine writes a block of configuration data for a PCI Express virtual function (VF). This routine is called by the driver of a PCIe VF on a device that supports the single root I/O virtualization (SR-IOV) interface. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_VPCI_INTERFACE_STANDARD structure](ns-vpci-_vpci_interface_standard.md) | The VPCI_INTERFACE_STANDARD interface structure enables device drivers to access blocks of configuration data that is specific to a PCI Express (PCIe) virtual function (VF) of devices that support the single root I/O virtualization (SR-IOV) interface. |
| [_VPCI_INVALIDATE_BLOCK_OUTPUT structure](ns-vpci-_vpci_invalidate_block_output.md) | The VPCI_INVALIDATE_BLOCK_OUTPUT structure is used in an IOCTL_VPCI_INVALIDATE_BLOCK IOCTL request. |
| [_VPCI_READ_BLOCK_INPUT structure](ns-vpci-_vpci_read_block_input.md) | The VPCI_READ_BLOCK_INPUT structure is used in an IOCTL_VPCI_READ_BLOCK IOCTL request to read data from a specified configuration block of data for a PCI Express (PCIe) virtual function (VF). |
| [_VPCI_WRITE_BLOCK_INPUT structure](ns-vpci-_vpci_write_block_input.md) | The VPCI_WRITE_BLOCK_INPUT structure is used in an IOCTL_VPCI_WRITE_BLOCK IOCTL request to write data to a specified configuration block for a PCI Express (PCIe) virtual function (VF). |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_VPCI_INVALIDATE_BLOCK IOCTL](ni-vpci-ioctl_vpci_invalidate_block.md) | The driver for a PCI Express (PCIe) virtual function (VF) issues the IOCTL_VPCI_INVALIDATE_BLOCK IOCTL request in order to be notified of changes to data in one or more VF configuration blocks. |
| [IOCTL_VPCI_READ_BLOCK IOCTL](ni-vpci-ioctl_vpci_read_block.md) | The driver for a PCI Express (PCIe) virtual function (VF) issues an IOCTL_VPCI_READ_BLOCK I/O control code (IOCTL) in order to read data from a VF configuration block. The driver issues this IOCTL to the next-lower driver in the driver stack. |
| [IOCTL_VPCI_WRITE_BLOCK IOCTL](ni-vpci-ioctl_vpci_write_block.md) | The driver for a PCI Express (PCIe) virtual function (VF) issues an IOCTL_VPCI_WRITE_BLOCK I/O control code (IOCTL) in order to write data to a VF configuration block. The driver issues this IOCTL to the next-lower driver in the driver stack. |
