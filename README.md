## Test

# This is test repository for my own reference. 

# How to configure yum repo in redhat 

#steps:

1. Mount the ISO to any mounting point
2. Create repository file
3. Clean and update the repository 


#1. 
    ex. # mount -oloop /dev/cdrom  /mnt
    
#2  
    Create a file under /etc/yum.repos.d/ , this file must be .repo extenstion and add below content
    
    vi rhel.repo
    
    [Sharename]
    name=rhel-package
    baseurl=file:///mnt/
    enabled=1
    gpgkey=0  
    gpgkey=file:///etc/pki/rpm-gpg/KEY-FILE-NAME
    
   Save and exit (wq!)
   
#3. 
    If you encounter any error regarding gpekey , you should copy gpg key from repo ISO to /etc/pki/rpm-gpg/ and change the gpekey paramer in rhel.repo file. 
    
#4.

    Yum clean all 
    yum list all
    
 ##That's it. Thanks 
