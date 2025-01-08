# 🚀 Simple Web Application with AWS EC2 🌐

## 🖥️ Project Overview  
This project demonstrates how to deploy a basic web application on an AWS EC2 instance. It’s perfect for beginners looking to explore **AWS EC2**, **Linux server management**, and **web hosting**. 🎉  

---

## ✨ Features  
- 🌩️ Deploy a web application using **Apache** or **Nginx**.  
- 🔒 Secure instance access with SSH and `.pem` key pairs.  
- 🌍 Host a static website accessible over the internet.  
- 💡 Learn the basics of EC2 instance management.  

---

## 📚 What You'll Learn  
- How to launch and configure an EC2 instance.  
- Setting up a web server on **Ubuntu** or **Amazon Linux**.  
- Uploading files to the instance via SCP.  
- Configuring security groups to allow HTTP traffic.  

---

## ⚙️ Tools & Services Used  
- **AWS EC2**  
- **Apache** or **Nginx**  
- **SSH** & **SCP**  
- **HTML**  

---

## 🚀 Deployment Steps  

### 1️⃣ Launch EC2 Instance  
1. Log in to your AWS Management Console.  
2. Navigate to **EC2 > Launch Instance**.  
3. Choose an **Amazon Linux 2** or **Ubuntu** AMI.  
4. Select a **t2.micro** instance type (Free Tier eligible).  
5. Create or select a **Key Pair** (download the `.pem` file).  
6. Configure the instance with default settings and launch it! 🎉  

---

### 2️⃣ SSH into the Instance  
1. Open your terminal or PowerShell.  
2. Use the following command to connect:  
   ```bash
   ssh -i "MyKeyPair.pem" ec2-user@<Public-IP>
```

3. Replace `MyKeyPair.pem` with your key file and `<Public-IP>` with the EC2 instance's public IP.

---

### 3️⃣ Install Web Server

Run the following commands after SSH-ing into your instance:

#### Apache:

```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```

#### Nginx:

```bash
sudo apt update
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
```

---

### 4️⃣ Upload Your Web App

1. Transfer your `index.html` to the EC2 instance:
    
    ```bash
    scp -i "MyKeyPair.pem" /path/to/index.html ec2-user@<Public-IP>:~/
    ```
    
2. Move the file to the web server's root directory:
    - For Apache:
        
        ```bash
        sudo mv ~/index.html /var/www/html/
        ```
        
    - For Nginx:
        
        ```bash
        sudo mv ~/index.html /usr/share/nginx/html/
        ```
        

---

### 5️⃣ Configure Security Group

1. Navigate to **EC2 > Security Groups** in AWS.
2. Add an **Inbound Rule**:
    - **Type**: HTTP
    - **Protocol**: TCP
    - **Port Range**: 80
    - **Source**: 0.0.0.0/0 (or your IP for better security).

---

### 6️⃣ Access Your Web App

1. Open a browser and go to:
    
    ```plaintext
    http://<Public-IP>
    ```
    
2. 🎉 **Voila!** Your web application is live! 🎉

---

## 📂 File Structure

```plaintext
project/
├── index.html   # Your static web page
└── README.md    # This file
```

---

## 🌟 Real-World Applications

- Host static websites for personal or client projects.
- Build foundational knowledge for deploying scalable applications.
- Gain experience with AWS services for freelancing or career growth.

---

## 🤔 FAQs

### ❓ What if I lose my `.pem` file?

You won’t be able to SSH into your instance. To recover access, create a new Key Pair and attach it to the instance.

### ❓ Why can’t I access my web app?

- Ensure your Security Group allows HTTP traffic.
- Verify that your web server is running (`sudo systemctl status`).

---

## ❤️ Acknowledgments

Thanks to **AWS** and the open-source community for enabling seamless cloud deployments! 🚀

---

## 🏆 Author

- Built with ❤️ by PavanKumar Kothuri - Passionate about Cloud Computing and Web Development!
- 🌐 [LinkedIn Profile](https://www.linkedin.com/in/iamkpk/)
- 💻 [GitHub Profile](https://github.com/PavanKumarKothuri)  
- ✉️ [Email: pavankumarkothuri9@gmail.com](mailto:pavankumarkothuri9@gmail.com)

Feel free to connect with me for further discussions or contributions.
