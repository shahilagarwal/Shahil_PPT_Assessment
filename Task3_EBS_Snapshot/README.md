**Attach EBS Volume from Different AZ using Snapshot**

**Simple Definition**

Create a snapshot of an EBS volume and use it to create a new volume in a different Availability Zone (AZ), then attach it to another EC2 instance.

---

**Objective**

* Understand **EBS Snapshots**  
* Learn how to move storage across **Availability Zones**  
* Attach restored volume to another EC2 instance  
* Practice cross-AZ storage management in **Amazon Web Services**

---

**Concept Overview**

* **EBS Volume** → Storage attached to EC2  
* **Snapshot** → Backup of EBS stored in S3 (region-wide)  
* **Availability Zone (AZ)** → Isolated data center within a region  
* You **cannot directly attach a volume across AZ**  
* You must:  
  1. Create Snapshot  
  2. Restore Volume in target AZ  
  3. Attach to EC2

---

**Step-by-Step Implementation**

---

**Step 1: Check Existing Volume**

lsblk

Verify the volume you want to snapshot (example: /dev/nvme1n1).

---

**Step 2: Create Snapshot**

**🔹 Using AWS Console:**

1. Go to **EC2 Dashboard**  
2. Click **Volumes**  
3. Select your EBS volume  
4. Click **Actions → Create Snapshot**  
5. Add description  
6. Click **Create Snapshot**

---

**Step 3: Verify Snapshot**

1. Go to **Snapshots**  
2. Wait until status becomes **Completed**

---

**Step 4: Create New Volume from Snapshot in Different AZ**

1. Select the Snapshot  
2. Click **Actions → Create Volume**  
3. Choose:  
   * Same Region  
   * Different Availability Zone (Example: ap-south-1b if original was ap-south-1a)  
4. Click **Create Volume**

 Make sure your target EC2 instance is in the same AZ as this new volume.

---

**Step 5: Attach Volume to EC2**

1. Go to **Volumes**  
2. Select newly created volume  
3. Click **Actions → Attach Volume**  
4. Select target EC2 instance  
5. Device name: /dev/sdf  
6. Click **Attach**

---

**Step 6: Verify in EC2**

SSH into target EC2:

lsblk

You should see new device (example: /dev/nvme1n1).

---

**Step 7: Mount the Volume**

If filesystem already exists (because snapshot contains data):

sudo mkdir /mnt/restoredvol  
 sudo mount /dev/nvme1n1 /mnt/restoredvol

Check files:

cd /mnt/restoredvol  
 ls

You should see previously stored data.

---

**Step 8: Make Mount Persistent (Optional but Recommended)**

Find UUID:

sudo blkid

Edit fstab:

sudo nano /etc/fstab

Add:

UUID=your-uuid  /mnt/restoredvol  ext4  defaults,nofail  0  2

Save and test:

sudo mount \-a

 

 

 

