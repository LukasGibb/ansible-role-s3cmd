s3cmd
=====

An Ansible role that installs and configures s3cmd

Requirements
------------

You will need an AWS account and the keys for your s3 bucket.

Role Variables
--------------

See defaults/main.yml.

All variables sit under ```s3cmd``` key:

```
s3cmd:
  key: 'aws-key'
  secret: 'aws-secret'
  user: 'root'
```

    key: 'aws-key'

Your public IAM key.

    secret: 'aws-secret'

Your secret IAM key. Do not leave these in plain text. Use Ansible Vault or another key storage mechanism.

    user: 'root'

User to place the ```.s3cfg``` under. Defaults to the root user.

Dependencies
------------

None

Example Playbook
----------------

Obviously you will need to pass in your git repository details (not the example/default ones):

    - hosts: servers
      vars: 
        s3cmd:
          key: !vault |
          $ANSIBLE_VAULT;1.1;AES256
          63323533386339383539613336316431643164736666137386237663431636662313830366339333
          3136353663613838363735646635373631393665613036650a303332636635393139633962626362
          61366634343232363135306539356438373631623734316134616363376633323965353433643732
          3235623965336231320a643861346265646566373035362316462316433939636664336139653062
          62396464323938626463616663316632323638316364386564616465653036656462
          secret: !vault |
          $ANSIBLE_VAULT;1.1;AES256
          3243243228633938353613036650a303332613036650a30333213738623766343163666231383033
          666665366863393835396133363962323393665613036650a3033326366353931396339626263623
          23426663434323236313530653935643837363162373431613461636337663332396535343364373
          33232562366339333636633933366438613462656465663730353330353763393963666433613965
          46464323938626463616663316632323638316364386564623236383163643863
          user: 'root'

      roles:
        - lukasgibb.s3cmd


License
-------

MIT


Author Information
------------------

This role was created in 2019 by:
[Lukas Gibb](https://github.com/LukasGibb) from [CloudJourneyman.com](http://www.cloudjourneyman.com/)
