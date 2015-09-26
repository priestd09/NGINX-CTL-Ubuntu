#NGINX-CTL

A simple command line bash script for configuring nginx development hosts on a ubuntu machine.

## Usage

1. Clone the script to your ubuntu machine. `git clone https://github.com/ssddanbrown/NGINX-CTL-Ubuntu.git nginx-ctl`.
2. Enter the cloned folder and make the script executable. `cd nginx-ubuntu-ctl && chmod +x nginx-ctl`.
3. Run the script as with root privilages. `sudo ./nginx-ctl create` or `sudo ./nginx-ctl remove`

## Commands

#### Create `sudo ./nginx-ctl create`

This will ask for an app name, Project path and a nginx template. After these items have been entered the specified nginx configration template will be used to create a new nginx host. A line will be added to your /etc/hosts file so you can use the {app_name}.dev domain to access your project. 

Read below for information on the templating.

#### Remove `sudo ./nginx-ctl remove`

This will ask for an app name. Any projects added with the given name will be removed from nginx and your system /etc/hosts file.

## Nginx Templates

All templates are held within the `nginx-templates` folder which is located within the same location as the nginx-ctl script. Some templates are provided with the script for some popular frameworks & applications. You can use these as an example for creating new templates. 

The structure of these templates is very simple. They are just normal nginx config files with some special tags which are replaced when the script runs. Within these templates there are two template tags you can use:

* `{{{path}}}` - The project path you supply when running the create command.
* `{{{domain}}}` - The local domain to use which is the supplied app name with '.dev' appended.

