## Linux

####  1. Share files between RHEL5 and Windows using Samba
  * 1.1 Install samba server on RHEL5: `sudo yum install samba`
  * 1.2 Check status: `/etc/init.d/smb status`
  * 1.3 Modify configure file `/etc/samba/smb.conf`
  *  1.3.1 For `[workplace]` section, replace `/workplace` with any absolute direcotry `/path/you/want`
  *  1.3.2 Change owner and owing group of files: `sudo chown <user id>:domain /path/you/want`
  *  1.3.3 Change access permission `chmod 770 /path/you/want`
  * 1.2 Start samba: `sudo /etc/init.d/smb start`
  * 1.3 Start samba on boot: `sudo /sbin/chkconfig --levels=345 smb on`
  * 1.4 To modify `smb.conf`: create a new file with configures you want and run: `sudo cp /new/file/path/ /etc/samba/smb.conf`
  * 1.5 Each time after changing `smb.conf`, restart to take effects: `sudo /etc/init.d/smb restart`
  * 1.6 On Windows: type server name, i.e. RHEL5 hostname, followed by /path/you/want
  * 1.7 Network drive can also be mapped to hard drive


#### 2. System auditing service: Auditd
  * 2.1 Remove a watch: `auditdctl -W path` e.g. `auditctl -W /etc/hosts -p wa -k hosts-file`
  * 2.2 List all watches: `auditctl -l`
  * 
  

### TO-DO
1) remove watch

2) restore audit.rules

3) go through audit.log doc

4) try touch ssh_config example

5) https://www.redhat.com/archives/linux-audit/2013-October/msg00004.html

6) Search original doc saying that audit can capture commands


#### 3. she-bang

### Storage Virtualization
#### 1. Logical Volume
#### 2. Physical Volume
#### 3. Volume Groups


## Git
### 1. Push code on feature branch to master branch
#### 1.1 On feature branch
```
git rebase master  # need to deal with conflicts
git checkout master
git merge --squash feature
git status
git push
```
