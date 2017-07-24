===============================
HOW TO ACCESS GITHUB VIA SSHKEY
===============================

=====
STEP1
=====
+ If you do not have your ssh key yet, generate your sshkey by command 'ssh-keygen', and you'll get two file "id_rsa" and "id_rsa.pub".
+ Note that if you've already run ssh-keygen, your "id_rsa.pub" may already be renamed to "authorized_keys", make sure you can find your "id_rsa" as it may be renamed.

=====
STEP2
=====
+ Open your "id_rsa.pub", copy the content and paste it to "SSH and GPG keys" in your github profile

=====
STEP3
=====
+ create a file named "config" in '~/.ssh', content may look like below:

 .. code-block:: config 
  :linenos:
       host github
       HostName github.com
       User git
       IdentityFile /path/to/your/id_rsa


=====
STEP4
=====
+ Test your connect using 'ssh github', if you see:

  .. code-block:: config

     Hi yourname! You've successfully authenticated, but GitHub does not provideshell access.
     Connection to github.com closed.
  Then connection is successfully made.
+ Some tutorial says commend "ssh -T git@github.com" may also do the job. Note that if you have renamed your 'id_rsa', you may fail to connect to github.

=====
STEP5
=====
+ | Clone your repo from github.
  | After you copy your repo address from the website of github, it may look like:
  | "git@github.com:yourname/visit_github_via_sshkey.git"
  | Replace "git@github.com" with "github", for example, command:
  | "git clone github:yourname/visit_github_via_sshkey.git"
  | will successfully clone your repo to local machine.
