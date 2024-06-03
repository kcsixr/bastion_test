# bastion_test
Test task for engaging Bastion interny

1. In file hosts I defined group [managed_hosts] with example hosts node1 and node2 which for playbook will be applied.
2. Then I define role defaults in roles/user_password/defaults/main.yml
   I use username Test as task condition and test_pass as password that I set as default password for that user.
3. Next I create task as itself in roles/user_password/tasks/main.yml
   User's name and password are taken from defaults with encrypting password with sha512. Condition for changing password at first login is considered in string update_password.
4. Finally I created playbook with managed_nodes as hosts and we need to use root, so that's why string "become: yes" is added in playbook.
