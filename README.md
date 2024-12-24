# virtual-hosting-in-linux
Virtual hosting in Red Hat (or any Linux-based system) refers to hosting multiple websites or domains on a single server. This can be achieved using Apache HTTP Server (commonly known as Apache) or NGINX. Below is a guide to set up virtual hosting in Apache on a Red Hat-based system like RHEL.

# Steps to Set Up Virtual Hosting in Apache on Red Hat:
## 1. Install Apache
Ensure Apache is installed on your RHEL system. If not, install it using:

![Screenshot from 2024-12-25 00-04-23](https://github.com/user-attachments/assets/572508ae-a8d6-457d-bab8-7fe6a4cd250d)

## 2. Enable and Start Apache
Enable and start the Apache service to ensure it runs at startup.

![Screenshot from 2024-12-25 00-19-11](https://github.com/user-attachments/assets/fb60f5a8-1188-4a20-96fd-66e2d843172d)


## 3. Configure the Virtual Host Files

Apache uses virtual host configuration files to manage multiple sites.

Example Configuration for Two Sites:

- Create directories for the websites:

![Screenshot from 2024-12-25 00-26-56](https://github.com/user-attachments/assets/91766703-8472-480c-928d-e12468e9ad73)

---

- Set permissions:

![Screenshot from 2024-12-25 00-27-53](https://github.com/user-attachments/assets/ebf147f9-40a7-4905-b32a-e5bb666a0630)

---

- Add test content:

Site1

![Screenshot from 2024-12-25 00-30-47](https://github.com/user-attachments/assets/8b106aad-cfd5-44de-9d57-f6c5b27ef9b2)

![Screenshot from 2024-12-25 00-35-51](https://github.com/user-attachments/assets/03908777-d429-47f1-9220-3732eeab7f7c)

---

Site2

![Screenshot from 2024-12-25 00-34-22](https://github.com/user-attachments/assets/b6286d74-b383-46b3-9051-c6dd71f79075)


![Screenshot from 2024-12-25 00-33-39](https://github.com/user-attachments/assets/7e86e757-6515-41df-8fec-1d449172f3e9)

---

- Create virtual host configuration files: Virtual host files are stored in /etc/httpd/conf.d/.

Virtual Host : Create a file named vhost.conf

![Screenshot from 2024-12-25 00-47-18](https://github.com/user-attachments/assets/944cff06-4ea9-4a36-97a4-ac251e464e3d)


Add the following configuration:

![Screenshot from 2024-12-25 00-56-21](https://github.com/user-attachments/assets/61802b13-8fb1-4ff0-aacc-ff00b5b50e3e)




## 4. Update the hosts File (For Testing Locally)
To test locally without DNS setup, update the /etc/hosts file:

![Screenshot from 2024-12-25 01-18-56](https://github.com/user-attachments/assets/c4405686-e000-463a-85dc-7b6162aeaa77)


Add entries for your test domains:

![Screenshot from 2024-12-25 00-53-00](https://github.com/user-attachments/assets/d5246def-54f3-44cc-a499-b06758d6aed5)


## 5. Restart Apache
After making these changes, restart Apache to apply the configurations:

![Screenshot from 2024-12-25 01-14-42](https://github.com/user-attachments/assets/4ff236b3-83af-4857-9e36-4ab5fd02632a)



## 6. Test the Configuration

Open a web browser and navigate to:

- http://site1.local.com → Should display "Welcome to Site 1."

![Screenshot from 2024-12-25 01-02-49](https://github.com/user-attachments/assets/da311a3c-58f8-4bf1-a22f-cf6ce26b5712)

- http://site2.local.com → Should display "Welcome to Site 2."

![Screenshot from 2024-12-25 01-03-43](https://github.com/user-attachments/assets/c92377a0-ab96-4213-9733-43ced30c796a)



## Troubleshooting Tips

- Check Apache Syntax: Before restarting Apache, check for configuration errors:


![Screenshot from 2024-12-25 01-05-24](https://github.com/user-attachments/assets/6fe28d36-f504-43fe-9707-30d27850a883)


- Check Logs: If there are issues, check the Apache logs for errors:

      sudo tail -f /var/log/httpd/error_log

- Firewall Configuration: Ensure the firewall allows HTTP traffic:

![Screenshot from 2024-12-25 01-00-02](https://github.com/user-attachments/assets/22d6aac9-9b58-4165-9448-27674e435bce)

----

This setup enables you to host multiple websites on a single Red Hat server using Apache.
