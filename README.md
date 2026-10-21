# 🎬 Product Videos Workflow (n8n)

An easy, step-by-step explanation of what this n8n automation does and how to use it.

---

## 💡 What Does This Workflow Do?

In simple words:  
**You upload a simple product picture, and this automation automatically turns it into a high-quality studio photo and a 3D spinning video, then emails both back to you!**

```
[Fill Form & Upload Photo]
          ⬇️
[Save to Google Drive]
          ⬇️
[AI writes a photo prompt]
          ⬇️
[OpenAI makes a studio picture]
          ⬇️
[ImgBB creates a web link]
          ⬇️
[Runway creates a 10s rotating video]
          ⬇️
[Wait until video is ready]
          ⬇️
[Email photo & video to your inbox] ✉️
```

---

## 🚶 Step-by-Step Walkthrough

Here is what happens behind the scenes in plain English:

### 1. You Fill Out a Simple Form (`On form submission`)
You open a web form and provide:
- **Product Photo**: A normal picture of your product.
- **Product Title**: The name (for example, *Toothpaste* or *Wireless Headphones*).
- **Product Description**: A short note about the product.
- **Your Email**: Where you want the final files sent.

---

### 2. Save Photo to Google Drive (`Upload Photo`)
As soon as you click submit, the system saves your original photo safely inside a Google Drive folder named **"Product Creatives"**.

---

### 3. AI Writes the Best Instructions (`Product Photography Agent`)
An AI helper (powered by GPT-4) reads your product name and description. It writes a perfect description (prompt) explaining how to make the product look like it was photographed in a luxury studio with soft lighting and clean background.

---

### 4. Create the Studio Picture (`Create Image` & `Convert to File`)
The system takes your original photo and the AI description and gives them to OpenAI.  
OpenAI transforms the photo into a clean, commercial-ready studio photo.

---

### 5. Upload Image to Get a Web Link (`Get URL`)
The video generator needs a website link (URL) to see the picture.  
The workflow uploads the new photo to **ImgBB** (a free image host) to get a public link.

---

### 6. Make a 3D Spinning Video (`Generate Video`)
The photo link is sent to **Runway AI**.  
Runway makes a **10-second video** where the product slowly spins around in 3D like a premium commercial showcase.

---

### 7. Wait Until the Video is Ready (`Polling Loop`)
Video AI takes a little bit of time to render:
- The system waits **60 seconds** first.
- It asks Runway: *"Are you done yet?"*
- If it is still working, it waits **5 more seconds** and checks again.
- Once finished, it moves forward immediately.

---

### 8. Email the Results (`Send Finished Products`)
Finally, it sends an email from your Gmail account to the email you entered in Step 1.  
The email includes:
- 📷 Direct link to your new **Product Photo**
- 🎥 Direct link to your new **Product Video**

---

## 🔑 What Keys & Accounts Do You Need?

To run this workflow yourself, you only need 5 connections:

| Service | Why it is used | Cost / Type |
| :--- | :--- | :--- |
| **Google Drive** | Saves your uploaded photos | Free Google account |
| **Gmail** | Sends the final email with links | Free Google account |
| **OpenRouter** | Runs GPT-4.1 to write prompt instructions | API Key |
| **OpenAI** | Makes the studio photo | API Key |
| **ImgBB** | Stores image online so Runway can read it | Free API Key |
| **Runway ML** | Generates the 3D rotating product video | API Key |

---

## 🚀 How to Use It

1. Import `Product Videos.json` into your **n8n** dashboard.
2. Connect your credentials for Google, OpenRouter, OpenAI, ImgBB, and Runway.
3. Turn the workflow **Active** (or click "Test step").
4. Open the form link, upload your item photo, and click Submit.
5. Check your email after 1 to 2 minutes for your finished video and picture!
