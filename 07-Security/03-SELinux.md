#  Introduction to SELinux

[What is SELinux?](https://www.redhat.com/en/topics/linux/what-is-selinux)

SELinux defines access controls for the applications, processes, and files on a system. It uses security policies, which are a set of rules that tell SELinux what can or can’t be accessed, to enforce the access allowed by a policy. 

When an application or process, known as a subject, makes a request to access an object, like a file, SELinux checks with an access vector cache (AVC), where permissions are cached for subjects and objects.

If SELinux is unable to make a decision about access based on the cached permissions, it sends the request to the security server. The security server checks for the security context of the app or process and the file. Security context is applied from the SELinux policy database. Permission is then granted or denied. 

If permission is denied, an "avc: denied" message will be available in /var/log.messages.

## Introduction
- If a service such  as HTTPD is compromised then the attacker could potentially have access to all open permission files on your system. Essentially, SELinux defines at set of rules that determine what process can access specific files and location on a file system.
- A context is assigned to every process, directory, and port wich is used to determine if a process can access that specific resource.
- In this cou section will focus on the 'type' context.
- SELinux has three modes
    - Enabled
    - Passive
    - Disabled
        - Disables mus be configures in /etc/selinux/config and reboot must occur in order to enter into disabled mode. This is not suggested.
- Boolean: is conditional rule that allows runtime modification of the security policy without having to load a new policy. For example, to allow cgi scripts to be executed then you can anebale the **httpd_enable_cgi** boolean. The opposite is true if the administrator wants to just disable all cgi scripts on a system.
- Man pages:
    - Booleans(8)
    - Selinux(8)
    - Getsebool(8)
