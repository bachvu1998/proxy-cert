# proxy-cert
The public key of the Forward Proxy
Device

1.  Connect the device to your laptop without starting the Kobiton Desktop application. Additionally, make sure your device has a Wifi connection.

2. Get device UDID

To get the device UDID:

For Android devices, go to the Menu >Settings > About Phone > Status. The IMEI / IMSI / MEID should be present in the phone status setting.

For iOS devices, connect the device to your laptop. Then, in the Finder sidebar, choose your iPhone, then click in the header just under your phone’s name until you can see the UDID. Then, right click and choose Copy UDID.

3. Install Kobiton Certificate

Go to the link then download the latest Kobiton certificate from this repo https://github.com/kobiton/proxy-cert

If you can not download the certificate directly to your device, you can download to your laptop instead. Follow those below steps to push the certificate to your device.

In order to push the certificate to your devices:

For Android devices, make sure that your device is connected to your laptop then run this command in terminal

For more information about 'path-to-your-downloaded-certificate', to get the downloaded certificate path for adding in the command line, please go to the location folder, then drag in a random terminal window then copy that path.

adb push 'path-to-your-downloaded-certificate' 'sdcard’

Example: Because I downloaded the file to the file to my Downloads folder, I’ll go to my downloads folder, drag and drop to a random open terminal then I’ll get the path as “/Users/$(whoami)/Downloads/mitmproxy-cert.crt”. Finally, copy the path to the command then we will have the bellow result

adb push '/Users/$(whoami)/Downloads/mitmproxy-cert.crt' 'sdcard'

 

After that, the certificate will be found in Settings → Storage → Explore if you are using the adb command above.

For iOS devices, we suggest you use the Airdrop to send the certificate file to your devices.

To install the certificate

For Android devices, press on the certificate 

At this step, if your device has already set up a passcode, a pop up message will appear to tell you to input your device passcode → Input → Input the certificate name then click OK. Finally, the certificate will be automatically installed.

Otherwise, Input the certificate name then click OK → A pop up message will appear to tell you to set a lock screen PIN or password before you move further. If you fall into this case, then press OK → Choose whatever option you want to set up including Pattern, PIN, Password and creating a passcode. After finishing setting up passcode, the certificate will be automatically installed.

For iOS devices, go to Settings → General → Profiles → Choose the Kobiton Certificate Authority → Press Install on the top right corner of the Screen → Done. 

For iOS devices to run the network payload capture service, please make sure that our Kobiton certificate is enabled with full trust for root certificates by

Going to Settings → General → About → Certificate Trust Settings.

Look at the Enable Full Trust For Root Certificate table view and make sure that the Kobiton Certification Authority is ON (otherwise, just tap on the toggle button to turn it on) then your device is ready to go.


4. Remove your created passcode before moving further.