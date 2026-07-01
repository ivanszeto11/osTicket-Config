<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo" />
</p>

# osTicket - Post-Install Configurations

## Overview

This project demonstrates the post-installation configuration of an open-source help desk ticketing system, osTicket. We will explore settings in the admin panel, including Roles, Departments, Teams, Agents, Service Level Agreements (SLAs), and Help Topics. By the end of the lab, we will have a better understanding of the importance of these configurations to osTicket's functionality and how to modify them.  

### Environments and Technologies Used

- Microsoft Azure (Virtual Machines)
- Remote Desktop Connection
- Windows 11 Pro
- Internet Information Services (IIS)
- osTicket

### Skills Learned

- Configuring agent settings in the osTicket environment to manage permissions and access 
- Creating SLAs and Help Topics to categorize tickets

## Walk-through

### Objectives

1. Create a Role named Supreme Admin with full permissions
2. Create a Department for SysAdmins
3. Create a Team for agents who support the online banking system
4. Create two Agents: Jane in the SysAdmins department and John in the Support department
5. Configure the SLAs for Sev-A, Sev-B, and Sev-C
6. Create Help Topics for common help desk issues
7. Create a User 

For this project, we have the osTicket program installed on a Windows 11 Pro VM hosted in Microsoft Azure. First, we will create a Remote Desktop connection to the VM and go to the osTicket login page. We need to log in to an admin account in order to access the admin panel. 

<p align="center">
  <img width="1871" height="937" alt="osticket-setup-1" src="https://github.com/user-attachments/assets/bf5b9630-c12b-4a4b-9986-e1df0c0262d1" />
</p>

### Agent Panel vs. Admin Panel 

<p align="center">
  <img width="960" height="379" alt="osticket-setup-2" src="https://github.com/user-attachments/assets/f106d544-40f4-4214-ae5f-7e3b3a1431c2" />
</p>

Once we are logged in, we are placed in the agent panel. This panel is where help desk agents work on tickets. To get to the admin panel, click the **Admin Panel** button on the top-right of the screen. 

<p align="center">
  <img width="962" height="426" alt="osticket-setup-3b" src="https://github.com/user-attachments/assets/11d659a8-d926-4d30-acca-ea99bed37c5b" />
</p>

The above image shows the admin panel, where admins can manage the settings and configurations of the osTicket system. Here, they can create agent accounts, modify their permissions, create Help Topics, and much more. The **Agent Panel** button on the top-right of the screen toggles back to the agent panel.

### Configuring Roles

In osTicket, **Roles** are sets of permissions that are applied to Agents with the specific Role. This makes it easier to configure permissions for agents without having to set them for each person manually. Navigate to the Roles tab under the Agents tab to see the existing Roles. If we wanted to view or modify the permissions for a Role, we can click on the existing Role. To create a new Role, click the **Add New Role** button.  

<p align="center">
  <img width="960" height="381" alt="osticket-setup-4" src="https://github.com/user-attachments/assets/10ceb953-16b7-42d3-aca5-3d935f16dc97" />
</p>

We need to name our new Role. In this case, let's name it "Supreme Admin" since we will be giving this Role full permissions. 

<p align="center">
  <img width="960" height="429" alt="osticket-setup-5b" src="https://github.com/user-attachments/assets/4ae72238-1a0f-4913-916b-4813256e8af2" />
</p>

Next, we will select the permissions associated with this Role. The first set of permissions is for tickets and dictates the actions that agents can perform on tickets. For our purposes, we will select every permission. 

<p align="center">
  <img width="956" height="561" alt="osticket-setup-6b" src="https://github.com/user-attachments/assets/7db609be-f9de-443f-892b-ef74da0c83f6" />
</p>

The next tab is the Tasks section, which lists the permissions for actions that the agents can perform on tasks. Again, we will select all permissions. 

<p align="center">
  <img width="955" height="417" alt="osticket-setup-7" src="https://github.com/user-attachments/assets/008f17f6-2c5b-430f-90a5-9af9904a1824" />
</p>

The Knowledgebase section is last and contains the permission for modifying canned responses. We will select it and click **Add Role** to finish creating the new Role.

<p align="center">
  <img width="955" height="405" alt="osticket-setup-8" src="https://github.com/user-attachments/assets/0c3eb94b-5a89-4b2f-9033-d823ffae1bcd" />
</p>

### Configuring Departments

**Departments** determine ticket visibility and route tickets to the appropriate agents. In the Departments tab, we can see the existing Departments: the default Support department and the Maintenance department. To change the configuration of these Departments, we can click on them. We will start creating a new Department by clicking **Add New Department**. 

<p align="center">
  <img width="957" height="325" alt="osticket-setup-9" src="https://github.com/user-attachments/assets/1f041340-1e80-40e9-a366-9e432e89293e" />
</p>

The two fields that must be filled out to create the Department are the Parent field and Name field. If we select a Department in the Parent field, the Department we create will be created within the Parent Department. Agents with access to a Parent department inherit access to child Departments, but agents with access to child Departments do not inherit access to the Parent. By selecting Top-Level Department in the Parent field, our Department will not be nested in another Department. We will name the Department "SysAdmins". 
<p>
There are many more settings that control how tickets are handled when they are routed to this Department, but for the purposes of this project, we can leave them as the default. 

<p align="center">
  <img width="957" height="939" alt="osticket-setup-10" src="https://github.com/user-attachments/assets/3adf9ba3-9006-4bd0-9602-085623714bca" />
</p>

### Configuring Teams

**Teams** allow us to group agents from different Departments to work on a specific issue. 

<p align="center">
  <img width="957" height="296" alt="osticket-setup-11" src="https://github.com/user-attachments/assets/05a97717-fb6d-4fdf-a35f-c08c03a5e920" />
</p>

<p align="center">
  <img width="956" height="519" alt="osticket-setup-12" src="https://github.com/user-attachments/assets/1490b6d9-759c-414f-aa77-f7cac078b663" />
</p>

### Configuring Agents

<p align="center">
  <img width="955" height="340" alt="osticket-setup-13" src="https://github.com/user-attachments/assets/b24dcef7-4826-4233-9b41-d8b7beb12e7c" />
</p>

<p align="center">
  <img width="955" height="471" alt="osticket-setup-14" src="https://github.com/user-attachments/assets/ec244a68-c6c5-4aee-ab86-9bc0f80e75f9" />
</p>

<p align="center">
  <img width="643" height="383" alt="osticket-setup-15" src="https://github.com/user-attachments/assets/f1f95fc1-ea50-47e4-88e1-feb8cc0a41f9" />
</p>

<p align="center">
  <img width="955" height="369" alt="osticket-setup-16" src="https://github.com/user-attachments/assets/0e8b4e82-303f-4a4d-95d3-a5e67caf431d" />
</p>

<p align="center">
  <img width="957" height="438" alt="osticket-setup-17" src="https://github.com/user-attachments/assets/32c4cfa4-aba1-4505-baec-fb3c67148b85" />
</p>

<p align="center">
  <img width="955" height="476" alt="osticket-setup-18" src="https://github.com/user-attachments/assets/f3028fc5-f281-4520-8a00-158114c2d286" />
</p>

<p align="center">
  <img width="956" height="515" alt="osticket-setup-19" src="https://github.com/user-attachments/assets/77d5d23f-5820-4925-966a-648cad875f7f" />
</p>

### Configuring SLAs

<p align="center">
  <img width="957" height="298" alt="osticket-setup-20" src="https://github.com/user-attachments/assets/71153aff-83b6-4753-8798-3f3692e5cb62" />
</p>

<p align="center">
  <img width="955" height="503" alt="osticket-setup-21" src="https://github.com/user-attachments/assets/270d671c-e9f3-49cc-bf06-d05445d0e6e7" />
</p>

<p align="center">
  <img width="955" height="503" alt="osticket-setup-22" src="https://github.com/user-attachments/assets/89b43b90-b7ef-4eca-822d-b6db012273fe" />
</p>

<p align="center">
  <img width="955" height="503" alt="osticket-setup-23" src="https://github.com/user-attachments/assets/6ca49b4a-89d5-44af-9715-4296618abdd6" />
</p>

### Configuring Help Topics

<p align="center">
  <img width="957" height="414" alt="osticket-setup-24" src="https://github.com/user-attachments/assets/6636a5f5-2d1a-4402-97a9-94eeb91a207b" />
</p>

<p align="center">
  <img width="955" height="478" alt="osticket-setup-25" src="https://github.com/user-attachments/assets/f59a80e8-4b03-4e90-9cb9-7b745989d838" />
</p>

<p align="center">
  <img width="955" height="478" alt="osticket-setup-26" src="https://github.com/user-attachments/assets/595d2cee-1047-4006-8bd4-a307d6940fe4" />
</p>

<p align="center">
  <img width="955" height="478" alt="osticket-setup-27" src="https://github.com/user-attachments/assets/024b0c47-2fb9-4abd-b300-cf11bd0436f2" />
</p>

<p align="center">
  <img width="954" height="478" alt="osticket-setup-28" src="https://github.com/user-attachments/assets/d8b3ce82-083a-4d61-bfcf-32b3a3cdd049" />
</p>

<p align="center">
  <img width="956" height="478" alt="osticket-setup-29" src="https://github.com/user-attachments/assets/d72ad000-54ab-472f-81ee-2b3faa0e3cca" />
</p>

### Configuring Users

<p align="center">
  <img width="957" height="342" alt="osticket-setup-30" src="https://github.com/user-attachments/assets/bd468361-cdce-44fd-9d2c-70f26ab99f09" />
</p>

<p align="center">
  <img width="643" height="390" alt="osticket-setup-31" src="https://github.com/user-attachments/assets/42953f24-07c7-4d93-8ec2-2cba6f8ce53d" />
</p>
