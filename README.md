# Character Art Static Webpage

This repository contains a static webpage designed to showcase character art. 
The webpage is hosted on a server and served through Nginx using a push-based mechanism enabled by Ansible for deployment across multiple servers.

## Table of Contents
- [Introduction](#introduction)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Deployment](#deployment)
- [Usage](#usage)

## Introduction
This project demonstrates a simple, static HTML page designed to display character art and related content. 
It uses Nginx as a web server to serve the content and relies on Ansible for automated deployment across multiple instances.

## Project Structure
The main components of the repository include:
- `index.html` - The main HTML file for the static webpage.
- `deploy_webpage.yml` - Ansible playbook to install Nginx, start the service, and deploy the `index.html` page to the server.

## Prerequisites
- **Ansible** installed on the master server instance.
- **Nginx** installed on the servers where the webpage will be hosted.
- **SSH Key** for connecting and managing the server instances.

## Installation
1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-username/character-art-webpage.git
    cd character-art-webpage
    ```

2. **Set Up Ansible**:
   - Follow the instructions to install Ansible on your master instance.
   - Update the `/etc/ansible/hosts` file with the public IPs of the servers (server1, server2, server3).

3. **Prepare SSH Access**:
   - Copy your SSH key (e.g., `ansible-master-key.pem`) to the Ansible master instance to enable SSH connections with the servers.
   - Example:
     ```bash
     chmod 400 ~/ansible-master-key.pem
     ssh -i "~/ansible-master-key.pem" ubuntu@<master-instance-ip>
     ```

## Deployment

1. **Run the Ansible Playbook**:
   - The `deploy_webpage.yml` playbook installs Nginx, starts the Nginx service, and copies the `index.html` file to the default Nginx directory.
   - Run the playbook to deploy the site:
     ```bash
     ansible-playbook deploy_webpage.yml
     ```
     ![image](https://github.com/user-attachments/assets/fcb7f83e-323b-4f80-9965-55f408a06e34)


2. **Validate Deployment**:
   - Access each server’s IP in your browser to confirm that the webpage is served correctly.


## Usage
Once deployed, you can access the webpage by entering the public IP of any of the servers in your web browser.
 ![image](https://github.com/user-attachments/assets/f4025877-3fae-490c-8ea1-220c6d04fab5)
