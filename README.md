# **Virtualized Storage**

Course: DevOps

Mod: Week 1

Topic: Virtualized Storage

Amount of time: 1.5 hours

Author: Thomas Fowler

## **Lesson Objectives**

* Understand hard disk controllers, their purpose, and the various types.

* List the types of disk images and their similarities and differences.

* Describe the process by which cloning storage volumes happens.

--------------------------------------------

### **Hard Disk Controllers**

#### **Overview**

In order to provide storage for virtual machines, hypervisors
emulate hard disk controllers of various types. A brief summary of
each type can be found below.

--------------------------------------------

#### **IDE Controllers**

This is an early yet advanced disk controller that can emulate up
to 4 virtual drives, one of which being the CD/CD-ROM drive.
VirtualBox supports PIIX3, PIIX4, or ICH6A type IDE controllers.
This is helpful when importing VMs from other hypervisor environments
where a particular IDE controller type is expected.

--------------------------------------------

#### **SATA Controllers**

Serial ATA controllers are a newer standard than IDE and offer many
advantages in performance and capacity. Instead of 4 drives, SATA
can support up to 30 virtual drives. Additionally, this controller
consumes fewer resources than IDE and provides much faster throughput
for virutal drives.

SATA controllers operate over the newer protocol AHCI or Advanced
Host Controller Interface. This is the default controller for
newly created VMs in VirtualBox.

--------------------------------------------

#### **SCSI Controllers**

SCSI (Small Computer System Interface) is a legacy controller that can
support up to 15 drives on either the LSI Logic or BusLogic flavors
of the SCSI specification.

--------------------------------------------

#### **SAS Controllers**

SAS or Serial Attached SCSI is the serial version of the SCSI interface.
The relationship between SAS and SCSI is somehwat like that of SATA and
IDE. The SAS controller can support up to 255 devices or virtual drives.

--------------------------------------------

#### **USB Mass Storage Controllers**

The USB Mass Storage controller emulates flash or thumb drives and has a
distinct difference between the other controllers. Instead of appearing
as one PCI device, the USB Mass Storage controller presents a device for
every USB device connected to the controller.

--------------------------------------------

### **Virtual Disk Image Types**

There are four main types of virtual disk images that VirtualBox supports.
They are as follows:

#### **VDI**

VDI is the proprietary and preferred format used by VirtualBox. This
format is not portable across hypervisors and it is encouraged that
the VMDK format be used instead. The VMDK format is discussed in the next
section.

--------------------------------------------

#### **VMDK**

VMDK is the open and preferred format for virtual disk images. This format
is supported by other hypervisor manufacturers such as VMWare.

--------------------------------------------

#### **VHD**

VHD is Microsoft's format for virtual disk images and is portable to most
of its hypervisor products.

--------------------------------------------

#### **HDD**

HDD is a format used by the popular macOS application Parallels when
running Windows guest virtual machines on macOS devices.
