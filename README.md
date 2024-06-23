Step 1: Launch an EC2 Instance
Sign in to AWS Console:
    Open the AWS Management Console.

Navigate to EC2:
In the AWS Management Console, search for "EC2" and select it.

Launch Instance:
Click on "Instances" in the sidebar.
Click the "Launch Instance" button.

Choose an Amazon Machine Image (AMI):
Select an AMI.
Choose an instance type based on your requirements.
Click "Next: Configure Instance Details".

Configure Instance Details:
Configure instance details such as network settings, subnet etc.

Click "Next: Add Storage".
Add Storage

Configure storage settings for your instance.
Click "Next: Add Tags".

Add tags to your instance for better organization 
Click "Next: Configure Security Group".
Configure Security Group:

Create a new security group or select an existing one.
Configure inbound rules to allow SSH (port 22) and any other ports required by your Strapi application (e.g., HTTP, HTTPS).
Click "Review and Launch".
Review and Launch:

Review your instance configuration.
Click "Launch".
Create or Select Key Pair:

Choose an existing key pair or create a new one.

Launch Instance:
Click "Launch Instances".
Your EC2 instance will be launched.


Step 2: Connect to EC2 Instance
Open Terminal (or Command Prompt):

Connect to EC2 Instance:
Coonect your instance using EC2 connect
Once connected, you'll be in the home directory by default.


Step 3: Prepare EC2 Instance for Strapi
Update the package manager on your EC2 instance:
sudo yum update -y
sudo yum install -y nodejs npm

Install Yarn package manager globally:
sudo npm install -g yarn

Install PM2 globally for process management:
sudo npm install -g pm2

Clone your Strapi project from a Git repository:
git clone https://github.com/username/your-strapi-project.git

Navigate to your Strapi project directory and install dependencies:
cd your-strapi-project
yarn install

Build your Strapi project if necessary:
yarn build


Step 4: Start Strapi Server
Start Strapi Server with PM2 : 

Use PM2 to start the Strapi server (replace your-strapi-project with your actual project name):
pm2 start yarn --name "strapi" -- start
This command starts the Strapi server using PM2, which ensures it runs in the background and restarts on system reboots.

Access Strapi Admin Panel:
Once the server is started, access the Strapi admin panel via a web browser 
