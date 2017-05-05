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

## Python
###1. Mutable objects
```python
a = b = [] # make a, b reference to the same list (mutable)
# so if a.append(1), then b = [1]
# a = b = mutable variables, they are references to the same object

my_list = [[1] * 4] * 3 # my_list = [[1, 1, 1, 1], [1, 1, 1, 1], [1, 1, 1, 1]]
# if set my_list[0][0] = 5, then my_list = [[5, 1, 1, 1], [5, 1, 1, 1], [5, 1, 1, 1]]
# [x]*3 will make references to the same object if x is mutable
```
###2. [Mutable default argument](http://docs.python-guide.org/en/latest/writing/gotchas/)

###3. Everything is a reference in Python 
  + [passing arguments](http://www.python-course.eu/python3_passing_arguments.php)
  + [tutorialspoint](http://www.tutorialspoint.com/python/python_functions.htm)

###4. Unittest
  * [Mock()](https://docs.python.org/3.4/library/unittest.mock.html#the-mock-class)
```python
a = Mock()
# a.b.c is a Mock() object
# a.b.c.return_value is a Mock() object
my_class.my_class_method.return_value.my_another_class_method.return_value = 1  # first approach
my_class.my_class_method().my_another_class_method.return_value = 1  # second approach
# first approach is equivalent to second approach, and no need to declear:
my_class.my_class_method.return_value = Mock()
# cause sth.return_value will create a new Mock() object
```

