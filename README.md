## Quickstart

```
$ ansible-playbook --ask-vault-pass --ask-become-pass --ask-pass bootstrap.yml
$ ansible-playbook --ask-vault-pass run.yml
```

## Remote file structure

* `/node/apps` are were docker-compose stacks are installed.
* `/node/data` is where all the data is stored.
  * The media server uses `/node/data/media` as its "root":
    * `/node/data/media` is mounted to radarr so that it can uses hardlinks
      between downloads and final destination folder
    * `/node/data/media/downloads` is for tranmission downloads
    * `/node/data/media/movies` is where radarr places finished downloads,
      mounted for jellyfin
