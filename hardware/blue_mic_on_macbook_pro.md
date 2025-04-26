It sounds like your Blue microphone is initially recognized by your **MacBook Pro**, but then stops working. Here are some troubleshooting steps to fix the issue:

---

### **1. Check System Preferences**
- Go to **System Settings** → **Sound** → **Input** and make sure your **Blue microphone** is selected as the input device.
- Test by speaking into the mic and checking the **input level** bar.
- If the mic stops showing input, unplug and replug it.

---

### **2. Check MacBook’s Power & USB Ports**
- If your MacBook is in **low power mode**, it may disable USB devices.
- Try using a different **USB port** or a **powered USB hub** to ensure it gets enough power.

---

### **3. Reset Core Audio**
If your MacBook stops recognizing the microphone after some time, try resetting **Core Audio**:

1. Open **Terminal**.
2. Type:
   ```bash
   sudo killall coreaudiod
   ```
3. Press **Enter**.
4. Restart any apps using the microphone.

---

### **4. Disable App Conflicts**
Some apps (Zoom, Discord, GarageBand) might interfere with your mic. Try:
- Closing all apps except the one using the microphone.
- Testing in **Voice Memos** to see if it still stops working.

---

### **5. Check for Driver Conflicts**
- Go to **System Settings** → **Privacy & Security** → **Microphone**.
- Ensure your app has permission to use the microphone.
- If using **Blue Sherpa** (for tuning settings), try closing it.

---

### **6. Reset PRAM & SMC**
If nothing works, resetting PRAM and SMC can help.

#### **Reset PRAM (for Intel MacBooks)**
1. Shut down your MacBook.
2. Press and hold **Option + Command + P + R** when turning it back on.
3. Release after 20 seconds.

#### **Reset SMC (for Intel MacBooks)**
1. Shut down your MacBook.
2. Hold **Shift + Control + Option** and press the **power button** for 10 seconds.
3. Release and turn on your Mac.

For **M1/M2 Macs**, restart your Mac as they reset automatically.

---

### **7. Test on Another Device**
- Plug the microphone into another Mac or PC.
- If it still stops working, the issue is likely with the microphone itself.

---

If these steps don’t work, let me know which **MacBook model** and **macOS version** you're using, and I can suggest more tailored fixes!