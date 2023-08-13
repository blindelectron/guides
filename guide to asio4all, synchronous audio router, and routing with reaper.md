# welcome.

Welcome to this guide dedicated to introducing an advanced routing solution that surpasses traditional methods like VAC (Virtual Audio Cable) and even competes with OBS Studio's routing approach. Throughout this guide, we'll break down the essentials of this solution and guide you through its setup process.

# What This Guide Covers

In this guide, we'll cover the following key topics:
1. Understanding the Solution: We'll explain the concept behind this routing solution and highlight why it's a viable choice.
2. Installation and Setup: We'll walk you through the initial steps, helping you install Asio4all, Synchronous Audio Router, and Reaper.
3. Configuring Reaper: Learn how to set up Reaper to effectively work with Synchronous Audio Router for seamless operation.
4. Creating Virtual Devices: Discover the process of setting up virtual devices within Synchronous Audio Router, offering you more flexibility in audio routing.
5. Optimizing Hardware: Configure Asio4all and your hardware devices to work harmoniously with Synchronous Audio Router.
6. Configuring Reaper tracks, sends and hardware outputs. Learn how to configure Reaper tracks, sends and hardware outputs to best fit your routing requirements.
7. Final Tips and Troubleshooting: We'll provide additional insights and solutions to common issues you might encounter.
This guide is here to provide you with straightforward, informative instructions. Whether you're a content creator, musician, or simply interested in audio systems, you'll gain valuable knowledge to enhance your audio routing capabilities. Let's dive in and explore this advanced routing solution step by step.

## 1. Understanding the Solution

This routing solution involves three essential components: Asio4all, Synchronous Audio Router, and Reaper. Let's delve into each component, starting with Asio4all. Asio4all serves as a vital software piece, facilitating universal support for asio across various audio hardware. Additionally, it enables the consolidation of multiple audio devices into a single asio device. Asio4all provides the flexibility to finely select whether input, output, or both of a device are routed to the asio device. Moving forward, let's explore Synchronous Audio Router. This tool empowers you to augment existing asio devices with virtual channels that seamlessly map to virtual Windows audio devices (MME devices). It grants the capability to enforce precise audio routing for specific applications, a valuable feature when dealing with apps lacking dedicated audio settings. Lastly, let's discuss Reaper, a digital audio workstation (DAW) that serves as the central hub for our audio routing endeavors. Now, why opt for this particular solution? There are several compelling advantages. Foremost, the utilization of a comprehensive DAW like Reaper unlocks a realm of possibilities. It allows for real-time application of live effects, intricate audio routing utilizing hardware track outputs and sends, and it significantly streamlines the process once the initial configuration is established. In summary, this solution brings together the capabilities of Asio4all, Synchronous Audio Router, and Reaper to provide an advanced audio routing setup. This approach offers extensive benefits, enabling a full-fledged DAW experience, sophisticated audio routing, and a smoother workflow post-initial setup.

## 2. Installation and Setup

### 2.1 Installing Required Software

Before diving into audio routing, it's crucial to install the necessary programs. Begin with Asio4all, which provides a foundation for our setup.

1. **Asio4all Installation:**
   - Visit the [Asio4all download page](https://asio4all.org/about/download-asio4all).
   - Click on the link for your preferred language to initiate the download.
   - Once the download is complete, run the installer and follow the provided instructions.

2. **Synchronous Audio Router Installation:**
   - Proceed to the [Synchronous Audio Router GitHub releases page](https://github.com/eiz/SynchronousAudioRouter/releases/latest).
   - Click on "Assets" if it's not expanded already, and download the appropriate version:
     - Choose the x64 MSI for 64-bit systems, or the x86 MSI for 32-bit systems. If unsure, you're likely on a 64-bit system.
     - Before running the installer, we need to enable test signing due to Microsoft's open-source driver policies.
     - Open an administrator PowerShell window from the Start menu by right-clicking and selecting "Run as administrator."
     - In the PowerShell window, enter the following command: `bcdedit /set TESTSIGNING on` and press Enter.
     - You should see an output confirming the successful operation.
   - Reboot your system, then run the Synchronous Audio Router installer and follow instructions, including allowing the installation of drivers.

3. **Reaper Installation:**
   - Access the [Reaper download page](https://www.reaper.fm/download.php).
   - Choose the appropriate download link for your operating system.
   - Run the installer and follow the on-screen instructions.
   - Additionally, you'll need to install the following extensions:
     - [Osara](https://osara.reaperaccessibility.com/snapshots)
     - [SWS](https://www.sws-extension.org)

By meticulously installing Asio4all, Synchronous Audio Router, Reaper, and their associated extensions, you're setting the groundwork for a seamless audio routing experience. Remember to follow each program's specific installation instructions and to reboot your system if required. With the software in place, we're ready to delve into configuring these tools for optimal performance.

### 2.2 Initial Configuration of Reaper

Reaper will serve as the cornerstone of our setup. Let's begin configuring it to lay a solid foundation for our audio routing journey.

1. **Launching Reaper:**
   - Start by launching Reaper. Don't be surprised if it prompts you for a license or inquires about your evaluation status. It's worth noting that Reaper doesn't enforce payment; if you choose not to pay after the 60-day evaluation period, you can simply click "Still Evaluating."

2. **Accessing Reaper Preferences:**
   - Navigate within Reaper to the *Options* menu, then select *Preferences*. This will open up the preferences settings.

3. **Configuring Audio Settings:**
   - Within the preferences window, navigate to the *Audio* section.
   - Here, you'll find a checkbox labeled *Close audio device when stopped and application is inactive*. Uncheck this box.
   
This initial configuration within Reaper ensures that your audio device remains accessible even when Reaper is inactive, setting the stage for effective audio routing. In the next sections, we'll delve deeper into the setup process. We'll guide you through configuring Reaper to work harmoniously with the Synchronous Audio Router and make the most out of this advanced audio routing solution.


## 3. Configuring Reaper for Synchronous Audio Router

Now, let's ensure that Reaper is properly configured to work seamlessly with Synchronous Audio Router. This step is crucial for establishing a solid connection between these two components.

1. **Accessing Reaper Preferences:**
   - To begin, navigate to the *Options* menu in Reaper, then select *Preferences*. This will open the preferences settings window.

2. **Configuring Audio Device:**
   - Within the preferences window, head to the *Devices* section.
   - Locate the *Audio System* combo box and select **ASIO** as the audio system.

3. **Selecting ASIO Driver:**
   - In the *ASIO Driver* combo box, choose **Synchronous Audio Router** from the available options.

4. **Configuring ASIO Driver:**
   - Click on the *Configure ASIO Driver* button. This will lead you to the setup process in the next section, where we'll continue to refine your audio routing experience.

By configuring Reaper to use Synchronous Audio Router as the ASIO driver, you're paving the way for precise audio routing and enhanced control over your setup. In the upcoming section, we'll delve into the specifics of configuring Synchronous Audio Router to optimize your audio routing capabilities.

## 4. Setting Up Synchronous Audio Router Virtual Devices

Upon opening the ASIO configuration window, you'll encounter a list and several buttons. This window is where we'll establish the virtual devices using Synchronous Audio Router. The list will showcase the virtual devices we're about to create, and the buttons grant us the ability to manage these devices efficiently. Let's embark on creating your first virtual device:

1. **Adding a Virtual Device:**
   - To begin, click on the *Add* button within the ASIO configuration window.
   - Assign a name to your virtual device; for instance, you might choose "System Audio."
   - Specify whether the device will function as a *recording* or *playback* device. If using a screen reader, you may need to use the screen reader's object navigation function to reach this selection box.
   - Select the number of desired channels, then click *OK* to confirm.

A quick note on recording versus playback devices:
- **Recording Devices**: These allow you to route audio output from Reaper to be captured by other applications.
- **Playback Devices**: These enable audio from other applications or even your entire system to be sent to Reaper.

2. **Customize to Your Needs:**
   - Repeat the process for as many devices as you require. For instance, I use one recording device for my microphone and other desired audio and two playback devices to segregate communication app audio. This ensures that my communication partners don't inadvertently hear themselves.

By setting up these virtual devices through Synchronous Audio Router, you're establishing a tailored audio routing environment that aligns with your specific needs. This level of customization ensures a seamless and efficient audio workflow. In the following sections, we'll further refine your setup, optimizing your hardware devices and enhancing your overall audio routing experience.

## 5. Optimizing Hardware

### 5.1 Configuring Asio4all with Synchronous Audio Router

In our previous configuration steps within the ASIO configuration window, there's one crucial aspect we didn't cover: the *Hardware Interface* combo box. This component plays a pivotal role, and it's time to address it.

1. **Selecting Asio4all:**
   - Within the ASIO configuration window, locate the *Hardware Interface* combo box.
   - From the available options, choose **Asio4all** as your hardware interface. Note that if you're using a screen reader, you might need to utilize the object navigation function to access this combo box.

2. **Configuring Asio4all:**
   - After selecting Asio4all, click on the *Configure* button.
   
   - This step will guide you through the subsequent configuration process, which we'll explore in the next section. By opting for Asio4all as your hardware interface and configuring it in conjunction with Synchronous Audio Router, you're ensuring optimal compatibility and integration for your audio routing solution. The upcoming section will delve into the specifics of configuring Asio4all and your hardware devices, allowing you to achieve the best possible audio routing experience.

### 5.2 Configuring Asio4all and Hardware Devices

Now, let's dive into configuring Asio4all to work harmoniously with your hardware devices for enhanced audio routing precision.

1. **Fine-Tuning Asio4all Configuration:**
   - Once the Asio4all configuration window is open, click on the *Advanced* button. This provides you with a more refined selection of devices and settings.

2. **Selecting Hardware Devices:**
   - In the advanced settings, check the checkboxes next to all the hardware devices you wish to have access to.
   - For each device, you can also expand the options and selectively disable the microphone or speaker. This leaves them available for general Windows usage. Note that once you take control of any component of a device, it won't be accessible to Windows while Reaper is active.

3. **Adjusting Sample Rate:**
   - After selecting your devices, move both the *Microphone* and *Speaker* sliders to a value of 4. This setting ensures a sample rate of 48000 samples, which significantly enhances sound quality for most hardware setups.

4. **Finalizing Asio4all Configuration:**
   - With your adjustments made, you can now close the Asio4all configuration window.

5. **Applying Changes:**
   - Return to the still-open Synchronous Audio Router window.
   - Click *Apply*, followed by *OK*. These actions will solidify your changes within the Synchronous Audio Router.

In the upcoming section, we'll explore how to tailor Reaper's tracks, sends, and hardware outputs to precisely align with your unique audio routing requirements. This customization will allow you to fully harness the potential of your configured setup.

## 6. Configuring Reaper Tracks, Sends, and Hardware Outputs

In this section, we'll delve into the intricacies of configuring Reaper's tracks, sends, and hardware outputs to ensure your audio routing setup aligns perfectly with your requirements.

1. **Adjusting Preferences:**
   - Open the *Preferences* in Reaper and navigate to the *Input* and *Output Range* combo boxes.
   - Make sure you have the first and last channel of your new ASIO device selected. Note that you might need to temporarily switch the driver to *WaveOut* and then back to ASIO to see all channels.
   - Once you've made these selections, click *OK* in the preferences window.

2. **Configuring Master Track I/O:**
   - Open the I/O panel for the master track by clicking on *I/O* next to it in the Reaper mixer. Alternatively, if you're using Osara, press *Shift + I*.
   - Delete any existing hardware outputs that might have been selected by default.
   - Add both your headphones/speakers and your primary recording device to which you want all audio routed.

3. **Creating Tracks:**
   - Start by crafting a track for your microphone. Navigate to the *Track* menu and select *Insert New Track*. Alternatively, press *F2* if you're using Osara.
   - Give your track a descriptive name, such as *Main Microphone*.
   - Ensure you select the appropriate channels of your new ASIO device to utilize your microphone. This can be accomplished by right-clicking the track and navigating to the *Input* menu for stereo or mono options, depending on your microphone setup.

4. **Replicating for Other Devices:**
   - Repeat this process for all other hardware and virtual devices. The method is the same for both types of devices.

5. **Routing to Specific Hardware:**
   - If you wish to route a track to a specific hardware device, open the I/O panel for that track by selecting *I/O* or pressing *I* when using Osara.
   - Uncheck the *Master Send* checkbox, then select the desired hardware outputs. This ensures that the track's audio will be sent only to the specified hardware.

6. **Creating Send Tracks:**
   - To route tracks to your speakers, consider creating a send track. Create a new track and name it something like *Speaker Send*.
   - Access its I/O panel and uncheck *Master Send*. Add the appropriate hardware channels for your speakers.
   - In each track you want to send to your speakers, choose *Speaker Send* from the sends combo box.

With Reaper's tracks, sends, and hardware outputs thoughtfully configured, you're poised to take full advantage of your customized audio routing setup. In the next section, we'll wrap up our guide with final notes and potential troubleshooting tips.

## 7. Final Tips and Troubleshooting

This section is your go-to for resolving issues and uncovering extra tips that can enhance your audio routing experience. If you run into problems during the setup of this solution or are looking for additional insights, you're in the right place.

### Troubleshooting Common Issues

#### 1. Reaper Crashes During Audio Routing
One prevalent issue you might encounter is Reaper crashing when attempting to route audio through it. If you come across this problem, remember that it arises due to the requirement of having the same number of recording and playback devices. This parity is crucial for seamless operation.

#### 2. ASIO Fails to Take Over a Device
In situations where ASIO struggles to take control of a device, Windows might be blocking its access. To address this, you can disable the device in Windows:
   - Press Windows + R to open the Run box.
   - Type `mmsys.cpl` and hit Enter to access the Sound Control Panel.
   - Under both the *Playback* and *Recording* tabs, right-click on the device you want to disable and choose *Disable*.

### Maximizing Your Audio Experience

- **Live Effects with Reaper**: Given that Reaper is a DAW, you have the power to apply live effects to your microphone. This includes noise reduction, compression, and more. To do this, click *Effects* next to the track in the mixer, or if using Osara, press *F* on the track. Then, add your effects, adjust their settings, and instantly elevate your audio quality.

By troubleshooting potential issues and leveraging these tips, you'll be able to unlock the full potential of your advanced audio routing setup. With this guide at your fingertips, you're well-equipped to handle any challenges that may arise and make the most of this powerful solution.

## Conclusion

And there you have it, the journey comes to an end. This guide has equipped you with the knowledge to master advanced audio routing using Reaper, enabling you to elevate your entire audio experience. From seamless routing to diverse destinations to the application of live effects, you now have the tools at your disposal. With this newfound understanding, you can manipulate audio as you see fit, sending it wherever you need, even to multiple destinations simultaneously. The ability to enhance your audio through live effects is now within your grasp. Should any questions arise or if you seek further guidance, don't hesitate to reach out to me on Mastodon at `blindelectron@dragonscave.space`. Your inquiries are always welcome. Thank you for embarking on this journey, and may your audio routing endeavors be nothing short of exceptional.