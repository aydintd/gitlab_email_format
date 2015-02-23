# gitlab_email_format
GitLab E-mails on Push Notification Service modified e-mail formats

Replace these two files with their originals in : `$GITLAB_ROOT/app/views/notify`

If your gitlab is running on in production environment, make sure you restart the gitlab service after replacing.

E-Mails are going to arrive to the defined e-mail address like this :

            Commits:
            
            Repository: http://gitlab.aydintd.me/aydin/module-elasticsearch
            Branch: refs/heads/master
            
            Commit:  83b64d917c1c398f52541dc2df945df2cb509dee
            Link :   http://gitlab.aydintd.me/aydin/module-elasticsearch/commit/83b64d917c1c398f52541dc2df945df2cb509dee
            Author:  Aydın Doyak
            
            refs #12345 changed some values
            
            
            Changes:
            
            =====================================
            manifests/init.pp
            =====================================
            --- a/manifests/init.pp
            +++ b/manifests/init.pp
            @@ -10,7 +10,7 @@ class elasticsearch (
                    $conffile        = $elasticsearch::params::conffile,
                    $el_user         = $elasticsearch::params::el_user,
                    $el_group        = $elasticsearch::params::el_group,
                    -  $config_file     = "elasticsearch.yml.erb",
                    +  $config_file     = "elasticsearch.yml.haml",
                    $logdir          = $elasticsearch::params::logdir,
                    $el_install_dir  = $elasticsearch::params::el_install_dir,
                    $nodemaster        = $elasticsearch::params::nodemaster,
            
            =====================================
            manifests/params.pp
            =====================================
            --- a/manifests/params.pp
            +++ b/manifests/params.pp
            @@ -7,7 +7,7 @@ class elasticsearch::params {
                    $java_bin        = '/usr/bin/java'
            
                    $discovery_zen_ping_unicast_hosts = '["127.0.0.1"]'
                    -  $nodename          = 'elasticmember'
                    +  $nodename          = 'elasticuye01'
            
                    $es_heap_size       = '2048M' 
                    $bootstrap_mlockall = 'false'
            

        

