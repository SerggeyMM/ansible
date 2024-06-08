# ansible

C:\Users\User>git --version
git version 2.45.2.windows.1


C:\ansible>docker build -t ansible-docker .
[+] Building 173.1s (9/9) FINISHED                                                                       docker:default
 => [internal] load build definition from Dockerfile                                                               0.0s
 => => transferring dockerfile: 271B                                                                               0.0s
 => [internal] load .dockerignore                                                                                  0.0s
 => => transferring context: 2B                                                                                    0.0s
 => [internal] load metadata for docker.io/library/ubuntu:latest                                                   0.0s
 => [1/4] FROM docker.io/library/ubuntu:latest                                                                     0.0s
 => [internal] load build context                                                                                  0.0s
 => => transferring context: 1.60kB                                                                                0.0s
 => [2/4] RUN apt-get update &&     apt-get install -y software-properties-common &&     apt-add-repository --y  168.9s
 => [3/4] WORKDIR /ansible                                                                                         0.0s
 => [4/4] COPY . /ansible                                                                                          0.0s
 => exporting to image                                                                                             4.0s
 => => exporting layers                                                                                            4.0s
 => => writing image sha256:1c914532696d57c27095fa3d7dc21a2f90168855d1818f81bce7e8b7cb7637da                       0.0s
 => => naming to docker.io/library/ansible-docker                                                                  0.0s

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview



C:\ansible>docker run --rm -v %cd%:/ansible ansible-docker ansible-playbook -i /ansible/inventory.ini /ansible/homework.yaml

PLAY [Homework playbook for Netology ML] ***************************************

TASK [Gathering Facts] *********************************************************
ok: [localhost]

TASK [Ensure hosts are reachable] **********************************************
ok: [localhost]

TASK [Update package repository cache and install packages] ********************
changed: [localhost]

TASK [Create ansible user] *****************************************************
changed: [localhost]

TASK [Ensure /home/ansible directory exists] ***********************************
changed: [localhost]

TASK [Copy test.txt file to remote hosts] **************************************
changed: [localhost]

TASK [Create users and their home directories] *********************************
changed: [localhost] => (item=devops_1)
changed: [localhost] => (item=test_1)

PLAY RECAP *********************************************************************
localhost                  : ok=7    changed=5    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0