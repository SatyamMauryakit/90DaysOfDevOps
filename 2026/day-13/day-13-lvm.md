# Day 13 – Linux Volume Management (LVM)

## Introduction
LVM (Logical Volume Manager) allows flexible disk management.  
It lets me create, resize, and manage storage without unmounting disks.

LVM has three main layers:
- Physical Volume (PV) → Actual disk or partition
- Volume Group (VG) → Pool of storage made from PVs
- Logical Volume (LV) → Virtual partition created from VG

---

## Environment Preparation

Switched to root user:

sudo -i

Created virtual disk (loop device):

dd if=/dev/zero of=/tmp/disk1.img bs=1M count=1024  
losetup -fP /tmp/disk1.img  
losetup -a  

Observed device name: /dev/loop0 (example)

---

## Task 1 – Check Current Storage

Commands:
- lsblk
- pvs
- vgs
- lvs
- df -h

Explanation:
- lsblk → Shows disk and partition layout
- pvs → Shows physical volumes
- vgs → Shows volume groups
- lvs → Shows logical volumes
- df -h → Shows mounted filesystem usage

Observation:
- No LVM volumes existed before setup.

---

## Task 2 – Create Physical Volume (PV)

Command:

pvcreate /dev/loop0  
pvs

Explanation:
- Converts disk into LVM physical volume.

Observation:
- /dev/loop0 is now listed as PV.

---

## Task 3 – Create Volume Group (VG)

Command:

vgcreate devops-vg /dev/loop0  
vgs

Explanation:
- Creates storage pool named devops-vg.

Observation:
- devops-vg created successfully.

---

## Task 4 – Create Logical Volume (LV)

Command:

lvcreate -L 500M -n app-data devops-vg  
lvs

Explanation:
- Creates 500MB logical volume named app-data.

Observation:
- LV visible in lvs output.

---

## Task 5 – Format and Mount LV

Commands:

mkfs.ext4 /dev/devops-vg/app-data  
mkdir -p /mnt/app-data  
mount /dev/devops-vg/app-data /mnt/app-data  
df -h /mnt/app-data

Explanation:
- Formats LV with ext4 filesystem.
- Mounts LV to /mnt/app-data.

Observation:
- Filesystem mounted successfully.

---

## Task 6 – Extend Logical Volume

Commands:

lvextend -L +200M /dev/devops-vg/app-data  
resize2fs /dev/devops-vg/app-data  
df -h /mnt/app-data

Explanation:
- Increases LV size by 200MB.
- resize2fs grows filesystem.

Observation:
- Storage increased without unmounting.

---

## What I Learned

1. LVM allows resizing disks without downtime.
2. Storage is managed in layers (PV → VG → LV).
3. Logical volumes behave like normal partitions.

---

## Key Takeaway

LVM makes Linux storage flexible, scalable, and easy to manage.