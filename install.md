# Install the OS
do that

## get the device ID's for the drives

    ls /dev/desk/by-id | ~/HD_devices


# set up SSH connection

## create the key
cd ~/.ssh
ssh-keygen -t ed25519 -f [name]

## add the new OS to the ssh config file
nano ~./ssh/conf
Host [hostname]
    HostName [hostname]
    User trucktrav
    Port 22
    IdentityFile ~/.ssh/[name]

## add the key to the new OS
ssh-copy-id -i ~/.ssh/[name] [hostname]
eval ($ssh_agent)
ssh-add [name]


