## Build and Develop the Strapi Application

## Here I have attached my Strapi project explanation video uploaded to Google Drive. I faced some issues with Loom on my laptop, so I recorded and uploaded the video using Google Drive instead
https://drive.google.com/file/d/15DuYyxcfetZt3jumKjRoERasRDs-YH6D/view?usp=sharing

### ⚙️ Server Requirements
To run and develop a Strapi application smoothly, you need **at least 2 vCPUs and 8 GB RAM**.  
Otherwise, the server will lag heavily during the build process.

I initially tried using a **t3.medium with 2 GB swap**, but it was not sufficient.  
Finally, I chose **t3.large (2 vCPU, 8 GB RAM)**, which worked well.

---
### 🟢 Step 1: First clone the official strapi repo on our loacal machine using git
https://github.com/strapi/strapi

### 🟢 Step 2: Install Node.js and Yarn
Install Node.js on your machine.  
Then install Yarn globally:

### 🟢 Step 3: First install the nodejs on your machine and install the neccessary files.
Using the node install the "npm install -g yarn" because using this yarn we are going to build and develop the strapi.

### 🟢 Step 4: Once I build the code I didn't start. I was confused then after enquired the issue the strapi project files is inside the
examples folder /strapi/emaples/getstarted/

### 🟢 Step 5 : We should run the "yarn develop" command inside the folder only. Otherwise it won't run. It will give the error only.
Now can access the <ip>:1337/admin

### 🟢 Step 6: Finally we added the content files on strapi admin panel.
