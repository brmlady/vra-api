    config/               # this hierarchy represents a "role"
        tasks/            #
            main.yml      #  <-- tasks file can include smaller files if warranted
        handlers/         #
            main.yml      #  <-- handlers file
        templates/        #  <-- files for use with the template resource
            ntp.conf.j2   #  <------- templates end in .j2
        files/            #
            bar.txt       #  <-- files for use with the copy resource
            foo.sh        #  <-- script files for use with the script resource
        vars/             #
            main.yml      #  <-- variables associated with this role
        defaults/         #
            main.yml      #  <-- default lower priority variables for this role
        meta/             #
            main.yml      #  <-- role dependencies
        library/          # roles can also include custom modules
            library/                  # if any custom modules, put them here (optional)
            module_utils/             # if any custom module_utils to support modules, put them here (optional)
            filter_plugins/           # if any custom filter plugins, put them here (optional)
        module_utils/     # roles can also include custom module_utils
        lookup_plugins/   # or other types of plugins, like lookup in this case

The current GetStates.yaml play dumps everything in your VRA 8.1 environment into json files and if someone updates something it will create a new version.

Edit the vars/main.yml or execute the --extra-vars like below.
ansible-playbook GetStates.yaml --extra-vars "username_prompt=ENTERHERE-NOTWITHDOMAIN password_prompt='ENTERHERE' etc"