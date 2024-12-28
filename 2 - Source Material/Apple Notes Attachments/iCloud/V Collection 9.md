![[catalog-image.png]]

# V Collection 9
Serial
## 3009404956078848
Unlock Code
## A51BZ332

# **Native Access Error: "Please grant permission to NTK Daemon to install dependencies"**
## **Symptom**
When trying to start Native Access, the startup fails with the following error message:
**Please grant permission to NTK Daemon to install dependencies.** 

![[6275819833501.jpg]]

## **Solutions**
Please choose your operating system:
## Windows
## macOS
## **Preparation**
1. Restart your computer.
2. Open **Activity Monitor** from **Applications > Utilities > Activation Monitor.app**
3. Check if the following processes are running: **NTKDaemon**, **Native Access Helper**.
4. If they are running, select them and click the **X** button to stop them. 

![[7640064492317.png]]

## **Deleting the Plist Files and Folders**
1. Please delete the following files and folders:
- Macintosh HD > Library > Launchdaemons > com.native-instruments.NativeAccess.Helper2.plist
- Macintosh HD > Library > Privilegedhelpertools > com.native-instruments.NativeAccess.Helper2
- Macintosh HD > Users > *Your User Name* > Library > Preferences > com.native-instruments.Native Instruments.plist
- Macintosh HD > Users > *Your User Name* > Library > Preferences > com.native-instruments.NTKDaemon.plist
- Macintosh HD > Users > *Your User Name* > Library > Application Support > Native Instruments NTK (folder)
- Macintosh HD > Users > *Your User Name* > Library > Application Support > Native Instruments > Native Access (folder) *Note: the User Library folder is hidden. To access it, click on* ***Go*** *in the menu bar and press down the* ***Alt*** *key. You'll now find the Library entry in the menu.*

2. Empty the trash.
## **Restart NTKDaemon**
1. Open the **Applications** folder, right-click **Native Access** and select **Show Package Contents**. 

![[7640064496285.png]]

2. Navigate to: **Contents > Resources > daemon > mac** 

![[7640064568221.png]]

3. Right-click the **NTKDaemon Installer Mac** and select **Open**.
4. Follow the installation procedure.
## **Restart Native Access Helper**
1. Open **Terminal** from: **Applications > Utilities > Terminal.app**
2. Copy the following **command line**, paste it into **Terminal** and hit **Enter**:
**sudo launchctl enable system/com.native-instruments.NativeAccess.Helper2**
3. Enter your macOS password when prompted.
4. Start Native Access.
If the issue persists, please contact our [support team](https://support.native-instruments.com/hc/categories/360000053677-Download-Installation).


If you are a user of a; Clarett Thunderbolt, Saffire or Red interface, on macOS 10.13+ please see the following article **in addition** to the below steps: 
[My Clarett / Saffire / Red Interface is not working on Catalina / Mojave / High Sierra](https://support.focusrite.com/hc/en-gb/articles/115005086925) 
Click the Apple Logo (top left of your screen) > About This Mac > System Report > Hardware > USB, or Thunderbolt.
If your interface is being seen at a hardware level, the interface model will be displayed in the main window as shown below.  

<p style="text-align:center;margin:0">
![[Screen_Shot_2018-07-11_at_15.45.21.png]]

</p>
If your interface **is not** shown in System Report, please test with another USB or Thunderbolt cable and another USB or Thunderbolt port. If you are still unable to see the interface, please [Contact Support](https://support.focusrite.com/hc/en-gb/requests/new). 
If your interface **is** showing correctly in the System report but Focusrite Control still displays No Hardware Detected, please complete the following instructions: 
**1)** Ensure you have the latest version of Focusrite Control from the [Downloads](https://focusrite.com/downloads) page or from your Focusrite.com account.  The version number of Focusrite Control is shown in the bottom right of the software, so you can compare that version to the version on the Downloads page.
**2)** If you are using a Clarett **Thunderbolt** interface then please ensure you have allowed the driver to load as per [this article](https://support.focusrite.com/hc/en-gb/articles/115005086925). 
**3)** Ensure Focusrite Server is running, to do this: 
- Open Focusrite Control.
- Open Finder and go to:
	- **Applications** > **Utilities** > **Activity Monitor.**
		- Find '**FocusriteControlServer**’.
- Double-click on '**FocusriteControlServer**’ > Click ‘**Quit**’.

<p style="text-align:center;margin:0">
![[Quit_Server_Mac.png]]

</p>
The service will not quit and will remain in Activity Monitor, your interface should now be detected in Focusrite Control. 
If this does not work, please go to step 4: 
**4)** Please manually start this server, to do this go to: 
- Finder > Applications
- *Right-click* on **Focusrite Control** and go to:
	- **Show Package Contents** > **Contents** > **Library** > **LoginItems** 
- Double click on '**FocusriteControlServer**'. 

<p style="text-align:center;margin:0">
![[FocusriteControlServer.png]]

</p>
 Now please open Focusrite Control and your interface should be recognised.
**5)** Check your firewall or antivirus software is not blocking the ‘Focusrite Control Server’ from running. Note this is only relevant if you have 3rd party Firewall or antivirus software installed.    Focusrite Control Server should be added as a firewall exception automatically during installation. If the Focusrite Control server is not in Firewall Options you can add it by going to: 
- Finder > Applications.
- Right-click on Focusrite Control and go to:
	- **Show Package Contents** > **Contents** > **Library** > **LoginItems** - keep this open.
- Go to:
	- System Preferences > Security and Privacy > Firewall > Firewall Options.  
- Drag the '**FocusriteControlServer**' to the '**Firewall Options**' screen.
- Set '**FocusritecontrolServer**' to '**Allow all incoming connections**'.

<p style="text-align:center;margin:0">
![[Mac_Firewall_Settings.png]]

</p>
Please **drag the Focusrite Control application** itself into the **Firewall options** while doing this.

**Native Access Error: "Please grant permission to NTK Daemon to install dependencies"**
## **Symptom**
When trying to start Native Access, the startup fails with the following error message:
**Please grant permission to NTK Daemon to install dependencies.** 

![[6275819833501 1.jpg]]

## **Solutions**
Please choose your operating system:
## Windows
## macOS
## **Preparation**
1. Restart your computer.
2. Open **Activity Monitor** from **Applications > Utilities > Activation Monitor.app**
3. Check if the following processes are running: **NTKDaemon**, **Native Access Helper**.
4. If they are running, select them and click the **X** button to stop them. 

![[7640064492317 1.png]]

## **Deleting the Plist Files and Folders**
1. Please delete the following files and folders:
- Macintosh HD > Library > Launchdaemons > com.native-instruments.NativeAccess.Helper2.plist
- Macintosh HD > Library > Privilegedhelpertools > com.native-instruments.NativeAccess.Helper2
- Macintosh HD > Users > *Your User Name* > Library > Preferences > com.native-instruments.Native Instruments.plist
- Macintosh HD > Users > *Your User Name* > Library > Preferences > com.native-instruments.NTKDaemon.plist
- Macintosh HD > Users > *Your User Name* > Library > Application Support > Native Instruments NTK (folder)
- Macintosh HD > Users > *Your User Name* > Library > Application Support > Native Instruments > Native Access (folder) *Note: the User Library folder is hidden. To access it, click on* ***Go*** *in the menu bar and press down the* ***Alt*** *key. You'll now find the Library entry in the menu.*
2. Empty the trash.
## **Restart NTKDaemon**
1. Open the **Applications** folder, right-click **Native Access** and select **Show Package Contents**. 

![[7640064496285 1.png]]

2. Navigate to: **Contents > Resources > daemon > mac** 

![[7640064568221 1.png]]

3. Right-click the **NTKDaemon Installer Mac** and select **Open**.
4. Follow the installation procedure.
## **Restart Native Access Helper**
1. Open **Terminal** from: **Applications > Utilities > Terminal.app**
2. Copy the following **command line**, paste it into **Terminal** and hit **Enter**:
**sudo launchctl enable system/com.native-instruments.NativeAccess.Helper2**
3. Enter your macOS password when prompted.
4. Start Native Access.
If the issue persists, please contact our [support team](https://support.native-instruments.com/hc/categories/360000053677-Download-Installation).