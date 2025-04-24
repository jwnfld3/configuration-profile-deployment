
# Create and Deploy a Configuration Profile for Windows Devices

## Overview
This lab demonstrates how to create a configuration profile in Intune using the Settings Catalog to deploy settings such as OneDrive automatic sign-in or desktop wallpaper enforcement. Configuration profiles allow IT teams to define and enforce system settings across all managed Windows endpoints.

## Who / What / Where / When / Why

**Who:**  
Desktop Engineers at a national consulting firm responsible for Windows laptop provisioning.

**What:**  
A configuration profile will be created to enforce OneDrive automatic sign-in and ensure BitLocker encryption is enabled.

**Where:**  
Microsoft Intune Admin Center → Devices → Configuration profiles.

**When:**  
During the initial provisioning phase or when rolling out a new baseline config.

**Why:**  
To automate endpoint configuration, improve security posture, and reduce the need for manual setup during onboarding.

## Step-by-Step Instructions

### Step 1: Access the Intune Admin Center
Open a browser and go to:  
https://intune.microsoft.com  
Sign in using a Global Administrator or Intune Administrator account.

**Explanation:**  
This step grants access to the Microsoft Intune Admin Center, which is required to manage configuration profiles. Using a Global or Intune Administrator account ensures all necessary features are accessible.

---

### Step 2: Create a Configuration Profile
Navigate to:  
Devices > Windows > Configuration profiles  
Click **+ Create policy**  
![image](https://github.com/user-attachments/assets/117e2359-68e9-4c7e-995f-584b1aba00c1)

Set:  
- **Platform:** Windows 10 and later  
- **Profile type:** Settings catalog  
Click **Create**

**Explanation:**  
This initiates the configuration process. The selected platform and profile type define the target OS and the method for choosing settings. The Settings Catalog provides a comprehensive set of options tailored to modern Windows devices.

![image](https://github.com/user-attachments/assets/cf4ab85e-a3ae-4433-b79a-bffb0239f8c6)

---

### Step 3: Define Profile Settings
Name the profile:  
Baseline - OneDrive & BitLocker  
Click **Next**, then **+ Add settings**  

![image](https://github.com/user-attachments/assets/3f084296-17d8-47a9-90ee-bbae2b8b099e)


Search for and add:
- **OneDrive > Silently sign in users to the OneDrive sync app with their Windows credentials** → Enabled  

![image](https://github.com/user-attachments/assets/d1875b88-0004-46ca-a84e-04083d01e697)

- **BitLocker > Require BitLocker** → Enabled  
Click **Next**

**Explanation:**  
Naming the profile helps in future identification. The settings selected enforce OneDrive auto sign-in and BitLocker encryption—critical for file synchronization and data protection. These policies help standardize and secure device behavior across the organization.

![image](https://github.com/user-attachments/assets/4e7b0527-235b-4878-8269-4c1d24fbce51)
![image](https://github.com/user-attachments/assets/c3aa3bb4-3a4e-42e5-a618-f88a101a5653)

---

### Step 4: Assign the Profile
Under **Assignments**, choose a device group (e.g., All Laptops or All Windows Devices).  
Optionally, apply filters for OS or device attributes.  
Click **Next**

**Explanation:**  
Assignments determine which devices will receive the settings. Filters can further refine deployment, ensuring that only the appropriate endpoints are targeted. This approach supports dynamic, automated policy delivery without manual intervention.

![image](https://github.com/user-attachments/assets/92a5b86a-ad79-4c5d-94dc-9798759304c8)

---

### Step 5: Review and Create
Review all configuration settings and group assignments.  
Click **Create**

**Explanation:**  
This final review allows validation of all selections. Once confirmed, creating the profile will deploy it to the targeted devices, initiating policy enforcement.

![image](https://github.com/user-attachments/assets/8425822b-b435-4717-8711-0eebfecb97ec)

---

### Step 6: Verify Settings on a Target Device
On a Windows device targeted by the profile:
1. Open **Settings > Accounts > Access work or school**, and click the connected work account.
2. Select **Info** and click **Sync** to force a policy update.
3. Open **OneDrive** and confirm it is signed in automatically with the work account.
4. Open **Control Panel > BitLocker Drive Encryption** and confirm BitLocker is turned on.

**Explanation:**
This step confirms that the assigned settings are functioning as intended on an actual endpoint. Verifying on a live device provides assurance that the configuration profile is effective and properly enforced.

---

## Conclusion
This configuration profile automatically enforces OneDrive login and BitLocker encryption, supporting secure and consistent Windows device deployments. Configuration profiles eliminate the need for manual registry edits or Group Policy changes, allowing scalable enforcement of key settings through Microsoft Intune.
